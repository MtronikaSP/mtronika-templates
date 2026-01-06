# WF-WD-04: Design Template Workflow Documentation

## Overview
Automated workflow that generates production-ready one-page websites for client projects. Uses AI agents to select templates, customize content, apply branding, and perform QA validation.

**Version:** v2.0  
**Last Updated:** 2026-01-05  
**Status:** Production Ready ✅

---

## Workflow Summary

```
Webhook → Get Project → AI Planning → Fetch Template → Inject Variables 
→ AI Customization → QA Validation → Save to Database → Email Notification
```

**Total Execution Time:** ~30-60 seconds  
**Success Rate:** 95%+ (with Phase 5 error handling)

---

## How It Works

### 1. Trigger (Webhook)
- **URL:** `https://omo.mtronika.co.za/webhook/start-design`
- **Method:** POST
- **Payload:** `{"project_ref": "WD-2026-XXXXXXXX"}`

### 2. Fetch Project Data (MySQL)
Retrieves client details from `projects` table:
- `client_name`, `client_phone`, `client_email`
- `industry_sector`, `business_intent`
- `brand_colour` (hex color, default: `#FD5D14`)

### 3. AI Planning Agent (Claude Haiku 3.5)
**Purpose:** Select best template based on industry and business intent

**Input:**
- Industry sector (e.g., "construction", "retail")
- Business intent (e.g., "showcase past projects")

**Output:**
```json
{
  "selected_template": "construction/template_a_v1",
  "status": "CONFIRMED"
}
```

**Templates Available:** 27+ templates across 15 industries  
**Repository:** `MtronikaSP/mtronika-templates` (GitHub)

### 4. Fetch Template & Blueprint (GitHub)
- **Template:** `index.html` (single-page with embedded CSS/JS)
- **Blueprint:** `blueprint.md` (template structure guide)
- **Base64 Decoding:** Automatically handled in `Inject Variables` node

### 5. Inject Variables & Image Placeholders
**Variables Replaced:**
- `{{business_name}}` → Client name
- `{{phone}}` → Client phone
- `{{email}}` → Client email
- `{{brand_colour}}` → Hex color
- `{{whatsapp}}` → WhatsApp number (formatted)

**Image Placeholder System:**
- Converts relative paths (`img/hero.jpg`) → Picsum.photos CDN
- Seed: `project_ref` (ensures consistent images per project)
- Dimension hints: carousel (1200x600), team (400x400), service (600x400), etc.

**Example:**
```html
<!-- Before -->
<img src="img/hero.jpg">

<!-- After -->
<img src="https://picsum.photos/seed/WD-2026-MJYTE3HF-1/1200/600">
```

### 6. AI Senior Dev Agent (Google Gemini 2.0 Flash)
**Purpose:** Customize HTML content to match client's business

**Tasks:**
1. Rewrite generic text → client-specific copy
2. Add CSS variable override for brand color
3. Integrate WhatsApp contact links
4. Update footer: "© 2026 [Client Name]. Designed by Mtronika."

**Output:** Full HTML document wrapped in markdown code block

### 7. AI Reflection Agent (Google Gemini 2.0 Flash)
**Purpose:** QA validation

**Checks:**
- No `{{handlebars}}` remaining
- Valid HTML structure (DOCTYPE, html, head, body)
- CSS styling present

**Output:**
```json
{
  "status": "QA_PASS",
  "error_log": "",
  "quality_score": 90
}
```

### 8. Database Update (MySQL)
**Table:** `projects`  
**Field:** `processed_html` (stores final HTML)  
**Status:** `deployment_status` → `Design_Complete`

### 9. Audit Logging (Phase 5)
**Table:** `workflow_audit`  
**Tracks:**
- Template used
- Variables injected count
- Images converted count
- QA status & score
- HTML size
- Timestamp

### 10. Webhook Response & Email
**Webhook Response:**
```json
{
  "status": "design_complete",
  "project_ref": "WD-2026-MJYTE3HF",
  "template_used": "construction/template_a_v1",
  "variables_injected": 11,
  "images_converted": 22,
  "qa_status": "QA_PASS",
  "qa_score": 90
}
```

**Email:** Admin notification with preview link

---

## Prerequisites

### Database Tables Required
```sql
-- Main projects table (must have brand_colour column)
ALTER TABLE projects 
ADD COLUMN brand_colour VARCHAR(7) DEFAULT '#FD5D14';

-- Error logging (Phase 5)
CREATE TABLE workflow_errors (
  id INT AUTO_INCREMENT PRIMARY KEY,
  project_ref VARCHAR(50),
  error_node VARCHAR(100),
  error_message TEXT,
  timestamp DATETIME,
  workflow VARCHAR(50),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);

-- Audit logging (Phase 5)
CREATE TABLE workflow_audit (
  id INT AUTO_INCREMENT PRIMARY KEY,
  project_ref VARCHAR(50),
  action VARCHAR(50),
  template_used VARCHAR(100),
  variables_injected INT,
  images_converted INT,
  qa_status VARCHAR(20),
  qa_score INT,
  html_size INT,
  timestamp DATETIME,
  workflow_version VARCHAR(50),
  created_at TIMESTAMP DEFAULT CURRENT_TIMESTAMP
);
```

### Required Credentials
1. **MySQL** → Database connection
2. **GitHub OAuth** → Template repository access
3. **Anthropic API** → Claude Haiku 3.5 (Planning Agent)
4. **Google Gemini API** → Gemini 2.0 Flash (Senior Dev & Reflection)
5. **SMTP** → Email notifications

### GitHub Repository
- **Repo:** `MtronikaSP/mtronika-templates`
- **Structure:**
  ```
  templates/
    ├── construction/
    │   ├── template_a_v1/
    │   │   ├── index.html
    │   │   └── blueprint.md
    │   └── template_b_v1/
    ├── retail-e-commerce/
    │   ├── template_a_v1/
    │   ├── template_b_v1/
    │   └── template_c_v1/
    └── ...
  ```

---

## Testing

### Manual Test
```bash
curl -X POST https://omo.mtronika.co.za/webhook/start-design \
  -H "Content-Type: application/json" \
  -d '{"project_ref": "WD-2026-MJYTE3HF"}'
```

### Expected Success Indicators
1. ✅ Webhook returns status 200
2. ✅ Email received within 60 seconds
3. ✅ Database `processed_html` field populated
4. ✅ `deployment_status` = `Design_Complete`
5. ✅ HTML contains brand color override
6. ✅ Images use Picsum.photos URLs

### Validation Checklist
- [ ] Open HTML in browser → renders correctly
- [ ] Check brand color on buttons/navbar
- [ ] Verify client name in header/footer
- [ ] WhatsApp link functional (if phone provided)
- [ ] No `{{handlebars}}` visible
- [ ] Images load from Picsum.photos

---

## Troubleshooting

### Common Issues

#### 1. "Model output doesn't fit required format"
**Cause:** Structured Output Parser enabled on AI agent  
**Fix:** Disable "Require Specific Output Format" toggle on AI nodes

#### 2. "Cannot read properties of undefined (reading 'content')"
**Cause:** GitHub returns base64-encoded content  
**Fix:** Ensure `Inject Variables` and `Agent - Senior Dev Prompt` decode base64:
```javascript
templateContent = Buffer.from(templateRaw, 'base64').toString('utf8');
```

#### 3. Images not showing
**Cause:** Relative paths not converted  
**Fix:** Verify `Inject Variables` node has image placeholder regex logic

#### 4. QA fails with "HTML structure incomplete"
**Cause:** Reflection Agent only sees truncated samples  
**Fix:** Update prompt to acknowledge it's seeing samples, not full HTML

#### 5. Brand color not applied
**Cause:** `brand_colour` column missing in database  
**Fix:** Run `ALTER TABLE projects ADD COLUMN brand_colour VARCHAR(7)`

---

## Monitoring & Maintenance

### Check Error Logs
```sql
SELECT * FROM workflow_errors 
WHERE created_at > DATE_SUB(NOW(), INTERVAL 24 HOUR)
ORDER BY created_at DESC;
```

### Check Audit Logs
```sql
SELECT 
  action,
  COUNT(*) as total,
  AVG(qa_score) as avg_score,
  AVG(html_size) as avg_size
FROM workflow_audit
WHERE created_at > DATE_SUB(NOW(), INTERVAL 7 DAY)
GROUP BY action;
```

### Performance Metrics
- **Avg Execution Time:** 45 seconds
- **Avg HTML Size:** 80-120 KB
- **Avg QA Score:** 90+
- **Variables Injected:** 11-15 per project
- **Images Converted:** 20-30 per template

---

## Version History

### v2.0 (2026-01-05) - Current
- ✅ Added Phase 2: Parser fixes for Gemini `.output` format
- ✅ Added Phase 3: Picsum.photos image placeholder system
- ✅ Added Phase 4: Enhanced AI prompts with content customization
- ✅ Added Phase 5: Error logging & audit tracking
- ✅ Upgraded AI models to Gemini 2.0 Flash
- ✅ Fixed base64 decoding for GitHub templates

### v1.0 (2025-12-XX) - Initial
- Basic template selection and variable injection
- Used Claude for all AI tasks
- No image placeholder system
- No QA validation

---

## Support

**Questions?** Contact: Kanyo M (Owner)  
**Issues?** Check `workflow_errors` table first  
**Template Updates?** Push to `MtronikaSP/mtronika-templates` on GitHub

---

## Quick Reference

| Node | Purpose | AI Model | Critical? |
|------|---------|----------|-----------|
| Webhook - Start Design | Trigger | - | ✅ |
| MySQL - Get Project | Fetch data | - | ✅ |
| AI Planning Agent | Template selection | Claude Haiku 3.5 | ✅ |
| GitHub - Get Template | Fetch HTML | - | ✅ |
| GitHub - Get Blueprint | Fetch structure guide | - | ⚠️ |
| Inject Variables | Replace placeholders + images | - | ✅ |
| AI Senior Dev Agent | Customize HTML | Gemini 2.0 Flash | ✅ |
| AI Reflection Agent | QA validation | Gemini 2.0 Flash | ⚠️ |
| MySQL - Update Design Status | Save HTML | - | ✅ |
| Respond to Webhook | Return status | - | ⚠️ |
| Send Email - Admin | Notification | - | ⚠️ |

**Legend:**  
✅ = Critical (workflow fails without)  
⚠️ = Important (workflow continues without)

---

## 💾 Prompt Caching (v3.0 - Cost Optimization)

### What is Prompt Caching?
Claude's prompt caching feature allows you to cache static portions of your prompts, reducing API costs by up to **75%** for repeated requests with similar system instructions.

### When to Use
- High-volume website generation (10+ sites/month)
- Repetitive AI tasks with static system prompts
- Cost-sensitive production environments

### How It Works

**Traditional API Call:**
```
Request 1: System Prompt (4K tokens) + Client Data → Full cost
Request 2: System Prompt (4K tokens) + Client Data → Full cost
Request 3: System Prompt (4K tokens) + Client Data → Full cost
```

**With Prompt Caching:**
```
Request 1: System Prompt (4K tokens, CACHED) + Client Data → Full cost + cache creation
Request 2: System Prompt (READ FROM CACHE) + Client Data → 75% cheaper
Request 3: System Prompt (READ FROM CACHE) + Client Data → 75% cheaper
```

### Cost Savings Calculation

| Metric | Without Caching | With Caching |
|--------|-----------------|--------------|
| System prompt (4K tokens) | $0.012/request | $0.003/request |
| 100 websites/month | $1.20 | $0.30 |
| **Monthly Savings** | - | **$0.90 (75%)** |

### Workflow File
**Import:** `WF-WD-04-v3-prompt-caching.json`

### Key Implementation Details

#### 1. Enable Caching Header
```javascript
headers: {
  "anthropic-version": "2023-06-01",
  "anthropic-beta": "prompt-caching-2024-07-31",  // ← REQUIRED
  "x-api-key": "sk-ant-api..."
}
```

#### 2. Mark Cacheable Content
```javascript
const systemPrompt = {
  type: "text",
  text: "Your static system instructions...",
  cache_control: { type: "ephemeral" }  // ← ENABLE CACHING
};
```

#### 3. Keep Dynamic Content Separate
```javascript
const userPrompt = {
  type: "text",
  text: `Client: ${client_name}, Industry: ${industry}`
  // NO cache_control - changes per request
};
```

### Cache Behavior Notes
- Cache persists for **5 minutes** after last use
- **Minimum 1024 tokens** required for caching to activate
- First request creates cache (slight extra cost)
- Subsequent requests read from cache (75% cheaper)
- Cache is per-API-key, not shared between accounts

### Monitoring Cache Performance
Check response usage fields:
```javascript
const cacheMetrics = {
  cache_creation_tokens: response.usage?.cache_creation_input_tokens || 0,
  cache_read_tokens: response.usage?.cache_read_input_tokens || 0
};

if (cacheMetrics.cache_read_tokens > 0) {
  console.log('✅ CACHE HIT - Saved on tokens!');
} else {
  console.log('❌ CACHE MISS - Cache will be created');
}
```

### Migration from v2.0 to v3.0
1. Import `WF-WD-04-v3-prompt-caching.json` into n8n
2. Configure credentials (MySQL, GitHub, use HTTP Header Auth for Anthropic)
3. Update webhook URL in your trigger systems
4. Both v2.0 (LangChain nodes) and v3.0 (HTTP with caching) can run in parallel

---

**END OF DOCUMENTATION**

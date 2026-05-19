modes/_profile.md dosyasının sonuna 3 yeni bölüm ekle. Mevcut içeriği 
silme, sadece sona ekle.

---

## CRITICAL — Token Optimization Mandatory Rules

These rules apply to EVERY job evaluation. Token cost is the user's 
primary constraint.

### 1. NO HTML File Generation
DO NOT write a separate cv-cem-ozcelik-{company}.html file.
Generate the HTML content INTERNALLY and pass it directly to 
generate-pdf.mjs via stdin or a temporary file that gets deleted.
Alternatively: write HTML directly to a tmp location, generate PDF, 
delete HTML.
The user does NOT use HTML files anywhere — only the PDF matters.
Save: ~6-8K tokens per evaluation.

### 2. WebSearch Restraint
- Maximum 2 web searches per evaluation
- For known major companies (in tracked_companies), trust the notes 
  field — skip "is this real company" verification
- For salary, ONE search is enough — use profile.yml ranges as baseline
- NEVER fetch full Glassdoor/Levels.fyi pages — search snippets only

### 3. Report Brevity
- Block tables: 5-6 rows max, not 8-10
- Block F (Interview): 4-5 stories max, not 6-7
- Skip "Top 5 LinkedIn changes" unless user asks
- Skip detailed gap mitigation tables — one sentence per gap is enough

### 4. Skip Unnecessary Reads
- DO NOT run "node update-system.mjs check" on every evaluation
- Only check on user request

Target: <12K total tokens per evaluation, including PDF.

---

## Known Company Heuristic — Skip Re-Verification

Companies in portals.yml's tracked_companies list are PRE-VERIFIED.
For these, SKIP:
- Company existence verification searches
- Layoff news searches (unless JD has explicit red flags like 
  "restructuring" or "merger")
- Stability searches

Pre-verified Turkish companies include:
Iyzico, Trendyol, Hepsiburada, Insider, Getir, Bilyoner, Akbank LAB, 
Param, Papara, Dream Games, Spyke Games, Doktor Tıkla, Picus Security,
Peak Games, Bitaksi, Yildiz Tech (Yildiz Holding), Arabam.com, Shipday.

ONLY run salary search if not already cached. Use profile.yml's 
compensation section as primary reference.

---

## CRITICAL — Project Selection Diversity Rule

The user has 6 projects in the registry. The system has been defaulting 
to the same 3 (Credit Risk + Rossmann + Medical) for many evaluations.

NEW RULE: Before selecting top 3 projects, READ the Project Registry 
in this _profile.md file (section "Your Archetype Detection Override") 
and select projects that BEST match the JD signals — not just defaults.

Check every JD against these specific archetype matchings:

| If JD mentions... | MUST consider these projects |
|---|---|
| "personalization", "recommendation", "search", "rec sys" | Spark Recommendation Engine + Amazon AI Search Engine (these are PRIMARY for these signals) |
| "NLP", "text", "sentiment", "language", "embedding" | Sentiment LSTM Bi-LSTM + Amazon AI Search Engine |
| "vector database", "semantic search", "embeddings" | Amazon AI Search Engine (this is the PRIMARY anchor) |
| "demand forecasting", "time series", "supply chain" | Rossmann Demand Forecasting (primary anchor) |
| "fraud", "risk", "credit", "anomaly", "imbalanced" | Credit Risk Prediction (primary anchor) |
| "computer vision", "image", "medical", "X-ray", "CNN" | Medical Diagnostics CNN (primary anchor) |
| "MLOps", "deployment", "Docker", "FastAPI", "production" | Pick top match by domain, then add Rossmann (FastAPI showcase) or Credit Risk (Docker showcase) |
| "big data", "Spark", "distributed", "Databricks" | Spark Recommendation Engine + Amazon AI Search Engine |

If multiple categories match, blend: 1 primary + 1 transferable + 1 
breadth project. NEVER default to the same 3 for every evaluation.

Specifically for Bitaksi, Yıldız Tech, and Arabam.com (today's evaluations):
- Bitaksi (mobility, demand forecasting, anomaly): Rossmann → Credit Risk → 
  Spark Recommendation (segmentation = ride matching analog)
- Yıldız Tech (e-commerce, customer analytics, LLM): Amazon AI Search → 
  Spark Recommendation → Rossmann
- Arabam.com (marketplace, recommendation, computer vision plus): 
  Amazon AI Search → Spark Recommendation → Medical Diagnostics

---

Bu 3 bölümü ekle, kaydet. Bir sonraki evaluation'da bu kurallara uy.
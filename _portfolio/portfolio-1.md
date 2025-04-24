---
title: "Clustering Project"
excerpt: "Flask app for clustering text data from CSV files using transformer-based NLP<br/><img src='/images/500x300.png'>"
collection: portfolio
---

This project is a Flask-based web app that performs text clustering on CSV data — ideal for quickly identifying themes or duplicate content from unstructured text.

**How It Works**
- Upload a `.csv` file with `Title` and `Description`.
- Cleans and tokenizes text using a transformer-based model.
- Supports fixed clusters or auto-adjusted based on similarity threshold.
- Cosine similarity used for grouping.

**Why It Matters**
- ⚡ Fast: Handles a few hundred rows in minutes.  
- 🧠 Smart: Modern NLP embeddings for accurate clustering.  
- 🧰 Practical: Useful for deduplicating articles, grouping feedback, and more.

**Features**
- Flask-based web UI  
- Real-time clustering feedback  
- Downloadable clustered results  
- Adjustable clustering sensitivity or fixed count

---
title: "Walkability and Obesity Analysis"
excerpt: "Regression analysis of walkability's impact on obesity across U.S. counties<br/><img src='/images/500x300.png'>"
collection: portfolio
---

This project explores whether the EPA's National Walkability Index can predict obesity rates when controlling for socioeconomic and access-related variables.

**Key Question**
> Does walkability predict obesity rates when adjusting for other factors?

**📊 Data Sources**
- **EPA SMART Location Database** (walkability, job access, land use)
- **CDC PLACES** (obesity, healthcare access)
Merged by county FIPS codes.

**Methodology**
Multivariate OLS regression with controls for:
- Healthcare access (`ACCESS2_AdjPrev`)
- Population size (`TotalPopulation`)
- Job accessibility (`Ac_Total`, `Ac_Unpr`)
- Demographics (`Pct_AO0`)
- Income (`R_PCTLOWWAGE`)
- Walkability (`NatWalkInd`)

**📍 About NatWalkInd**
EPA's composite walkability score (0–20) including:
- Street connectivity
- Land use diversity
- Transit proximity

**📈 Key Findings**
- Adjusted R² = 0.385
- `NatWalkInd` statistically significant (p < 0.001)
- Coefficient = -0.8663: A 1-point rise in walkability reduces obesity by ~0.87 percentage points

---
title: "Advanced Paste for Windows"
excerpt: "Clipboard and template integration tool for email-heavy workflows<br/><img src='/images/500x300.png'>"
collection: portfolio
---

Advanced Paste is a productivity tool designed to reduce context-switching in repetitive communication tasks, especially emails. Developed with the Microsoft PowerToys team.

**The Problem**
- 28% of office time is spent on email.
- Existing tools require context switching.
- Leads to cognitive overload and inefficiency.

**The Solution**
- Seamless integration of clipboard and templates.
- Less app switching, more focus.
- Great for roles like Support Engineers with repetitive messaging needs.

**🎬 Demo Video**
<video width="100%" controls>
  <source src="/assets/ClipboardTemplate.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>

Or [click here to watch the video](assets/ClipboardTemplate.mp4).

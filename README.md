# McDonald’s Enterprise AI-Infused Data Pipelines on Databricks: <sub>Omni-Channel Guest Experience, Governance, and Domain-Driven Architecture</sub>
#### *Designing intelligent, governed, and scalable enterprise data products using Databricks, Unity Catalog, and AI-powered pipelines — aligned with McDonald’s global omni-channel strategy.*

--- 

## Repository Overview 

##### McDonald’s operates one of the most complex global omni-channel enterprises in the world — spanning in-restaurant POS, drive-thru, mobile apps, kiosks, delivery platforms, customer support, and global franchises.

This repository demonstrates how a Principal Enterprise Architect can:

- Bridge the gaps between Data, Software/Microservices, and AI teams
- Design AI-infused enterprise data pipelines
- Govern data at scale using Unity Catalog
- Enable omni-channel customer intelligence
- Apply Domain-Driven Design (DDD) to enterprise data products
- Translate raw, unstructured signals into business-ready intelligence

While the role itself may not neccessarily be hands-on coding, this repo proves architectural depth across:

- Enterprise data platforms

- Cloud-native patterns

- AI integration

- Governance & compliance

- Cross-domain collaboration

---

## Why This Matters to McDonald’s

#### McDonald’s strategic priorities include:

- Customer experience at global scale

- Consistency across channels

- Localized execution with centralized governance

- AI-enabled personalization

- Operational excellence

- This architecture shows how AI moves from experimentation into enterprise production.

---

## Architecture Vision: AI-Infused Enterprise Data Pipelines

##### While the complete architectural vision for a McDonald's Principal Achitect could be found at:   ,  ................the discussion and approach in this repository highlights one aspect of the core vision. 

##### <ins>From Traditional ETL to Intelligent Data Products</ins>

##### Traditional ETL pipelines:

- Can break on schema changes

- Struggle with unstructured data

- Require manual governance

- Do not understand meaning

##### *AI-Infused Pipelines transform raw data into intelligent, reusable enterprise assets.*

---

## Core Capabilities Demonstrated in This Project

#### 1. <ins>Understand Content</ins>
Sentiment analysis, classification, summarization

#### 2. <ins>Automate Governance</ins>
PII detection and masking using AI

#### 3. <ins>Self-Adapt</ins>
Grammar correction, entity extraction, schema evolution

#### 4. <ins> Globalize</ins>
Multilingual translation for global operations

> [!IMPORTANT]
> Please see Miscellaneous for snapshots of how AI functions are inserted on McDonald's customers' reviews data. Only the high level AI parts are shown in this project. Interested readers (with .ipynb IDEs) can also download the data and codes for this repository and run it as stand-alone project without the Data Lake/Databricks Unity Catalog backends.
> An example of how AI fucntions are used on McDocnald's customers' review data is shown below:
>
> <img width="980" height="405" alt="Image" src="https://github.com/user-attachments/assets/dd17d2ff-0724-4abf-aa4d-3e6e0618c215" />
> More examples are available under Miscellaneous

---

## High-Level Architecture

```markdown
# Medallion Architecture with AI Layer

┌───────────────────────────────────────────────┐
│          Omni-Channel Data Sources            │
│ Streaming data │ Batch data │ APIs            │
│(from Dine-in, Drive-thru, Delivery etc sources)     
└───────────────────────┬───────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────┐
│              Ingestion Layer                  │
│      (Auto Loader, JDBC, Partner Connectors)  │
└───────────────────────┬───────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────┐
│              Bronze Layer (Raw)               │
│             • Preserve raw data               │
│             • Append-only                     │
│             • Schema-on-read                  │
└───────────────────────┬───────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────┐
│         AI Transformation Layer               │
│  • `ai_classify()` - Fraud detection          │
│  • `ai_extract()` - Entity extraction         │
│  • `ai_mask()` - PII protection               │
│  • `ai_translate()` - Multilingual support    │
│  • `ai_summarize()` - Document summarization  │
└───────────────────────┬───────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────┐
│           Silver Layer (Cleaned)              │
│            • Validated data                   │
│            • Standardized schemas             │
│            • Business-ready                   │
└───────────────────────┬───────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────┐
│            Gold Layer (Curated)               │
│            • Domain-aligned                   │
│            • Aggregated metrics               │
│            • Feature engineered               
└───────────────────────┬───────────────────────┘
           ┌────────────┼────────────┐
           │            │            │
           ▼            ▼            ▼
    ┌──────────┐  ┌──────────┐  ┌──────────┐
    │  BI &    │  │ Micro-   │  │   ML     │
    │ Dashboard│  │ services │  │ Training │
    │          │  │ APIs     │  │ Pipeline │
    └──────────┘  └──────────┘  └──────────┘
```

---

## Enterprise Data Ingestion Patterns


| Source Category | Data Source | Ingestion Method | Pattern | Example Code |
|-----------------|-------------|--------|---------|--------------|
| **Cloud Storage** | S3, ADLS, GCS | Auto Loader | Streaming | ```python<br>spark.readStream.format("cloudFiles")<br>``` |
| **Enterprise Systems** | SAP, Oracle, Salesforce | JDBC / Connectors | Batch | ```python<br>spark.read.jdbc(url, table)<br>``` |
| **Streaming Platforms** | Kafka, Event Hubs | Structured Streaming | Real-time | ```python<br>spark.readStream.format("kafka")<br>``` |
| **Mobile & Web Apps** | Custom Apps | REST APIs | Event-driven | Python `requests` library |
| **Third-Party Platforms** | External Services | APIs | Scheduled | Cron jobs / Airflow DAGs |

#### McDonald’s Example Sources

- Mobile app reviews

- In-store feedback kiosks

- Delivery platform feedback

- Social media monitoring

- Customer support transcripts

---

## Databricks Setup (Free Edition + Unity Catalog)

<ins>Prerequisites</ins>:

- Databricks Free Edition

- Unity Catalog enabled

- Python notebooks

<ins>Setup Steps</ins>:

- Create a Databricks workspace

- Enable Unity Catalog

<ins>Create schemas</ins>:

- bronze

- silver

- gold

- Upload review datasets or connect APIs

<ins>Run notebooks in sequence</ins>:

- 01_ingest_raw_data

- 02_ai_enrichment

- 03_governance_masking

- 04_domain_data_products

---

## AI Functions Used (Enterprise-Ready)

| Function | Purpose |
|----------|---------|
| ai_analyze_sentiment() | Understand guest sentiment |
| ai_classify() | Route feedback to business domains |
| ai_extract() | Extract entities (location, staff, issues) |
| ai_mask() | PII protection (compliance) |
| ai_fix_grammar() | Normalize text |
| ai_translate() | Global language support |
| ai_summarize() | Executive-level insights |


### Databricks AI Functions Reference

| 🤖 AI Function | 🎯 Purpose | 📝 Example Use |
|----------------|------------|----------------|
| `ai_analyze_sentiment()` | Understand guest sentiment | Customer reviews, survey feedback |
| `ai_classify()` | Route feedback to business domains | Categorize support tickets |
| `ai_extract()` | Extract entities (location, staff, issues) | Identify problem areas in feedback |
| `ai_mask()` | PII protection (compliance) | GDPR/CCPA compliance for customer data |
| `ai_fix_grammar()` | Normalize text | Standardize user-generated content |
| `ai_translate()` | Global language support | Multi-language customer support |
| `ai_summarize()` | Executive-level insights | Condense long reports for management |

### Databricks AI Functions Reference

| 🤖 AI Function | 🎯 Purpose | 📝 Example Use |
|----------------|------------|----------------|
| `ai_analyze_sentiment()` | Understand guest sentiment | Customer reviews, survey feedback |
| `ai_classify()` | Route feedback to business domains | Categorize support tickets |
| `ai_extract()` | Extract entities (location, staff, issues) | Identify problem areas in feedback |
| `ai_mask()` | PII protection (compliance) | GDPR/CCPA compliance for customer data |
| `ai_fix_grammar()` | Normalize text | Standardize user-generated content |
| `ai_translate()` | Global language support | Multi-language customer support |
| `ai_summarize()` | Executive-level insights | Condense long reports for management |

## AI Function Capabilities

| Function | Primary Purpose | Common Use Cases | Input | Output |
|----------|----------------|------------------|-------|--------|
| `ai_analyze_sentiment()` | Sentiment analysis | Customer feedback, reviews, social media | Text | Positive/Negative/Neutral score |
| `ai_classify()` | Text categorization | Ticket routing, content tagging, spam detection | Text | Category labels |
| `ai_extract()` | Entity extraction | Identify people, places, products, issues | Text | Structured entities |
| `ai_mask()` | Privacy protection | Compliance with GDPR, HIPAA, PCI-DSS | Text with PII | Anonymized text |
| `ai_fix_grammar()` | Text normalization | Customer feedback cleanup, content standardization | Text | Corrected text |
| `ai_translate()` | Language translation | Global customer support, content localization | Text | Translated text |
| `ai_summarize()` | Content summarization | Executive reports, article summaries | Long text | Condensed summary |

# Databricks AI Functions Guide

## Core Functions & Applications

| Function | Purpose | Code Example | Business Value |
|----------|---------|--------------|----------------|
| **`ai_analyze_sentiment()`** | Analyze customer sentiment | ```python<br>df.withColumn("sentiment", <br>    ai_analyze_sentiment("feedback_text")<br>)<br>``` | Real-time customer satisfaction monitoring |
| **`ai_classify()`** | Categorize text into domains | ```python<br>df.withColumn("category", <br>    ai_classify("ticket_text", <br>    ["billing", "technical", "sales"])<br>)<br>``` | Automated ticket routing (40% faster) |
| **`ai_extract()`** | Extract key entities | ```python<br>df.withColumn("entities", <br>    ai_extract("review_text", <br>    ["location", "employee", "product"])<br>)<br>``` | Structured insights from unstructured data |
| **`ai_mask()`** | Protect sensitive data | ```python<br>df.withColumn("masked_text", <br>    ai_mask("customer_text", <br>    ["email", "phone", "ssn"])<br>)<br>``` | GDPR/CCPA compliance automation |
| **`ai_fix_grammar()`** | Normalize and correct text | ```python<br>df.withColumn("clean_text", <br>    ai_fix_grammar("user_input")<br>)<br>``` | Improved data quality for downstream processing |
| **`ai_translate()`** | Translate between languages | ```python<br>df.withColumn("english_text", <br>    ai_translate("original_text", "en")<br>)<br>``` | Global customer support unification |
| **`ai_summarize()`** | Create executive summaries | ```python<br>df.withColumn("summary", <br>    ai_summarize("long_report")<br>)<br>``` | 80% faster report generation for leadership |

## Implementation Workflow
1. **Data Ingestion** → 2. **AI Processing** → 3. **Insights Generation**









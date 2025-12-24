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

| AI Function | Primary  Purpose | McDonald's Use Cases | Business Value |
|----------------|------------|----------------|-------------------------|
| `ai_analyze_sentiment()` | Understand guest sentiment ( positive/Negative/Neutral scores, ), i.e, sentiment analysis | Customer reviews, social media sentiments | Real-time customer satisfaction monitoring |
| `ai_classify()` | Route feedback to business domains, text categorization | Categorize support tickets, ticket routing, content tagging, spam detection |Automated ticket routing (40% faster) |
| `ai_extract()` | Extract entities (location, staff, issues) | Identify problem areas in feedback, identify specific customers for targeted adverts, places, products, issues |Structured insights from unstructured data |
| `ai_mask()` | PII protection (compliance) | Compliance with GDPR, HIPAA, PCI-DSS for customer data |Improved data quality for downstream data pipelines | Automated compliance with various standards |
| `ai_fix_grammar()` | Normalize text | Standardize user-generated content, customer feedback cleanup | Improved data quality for downstream data pipelines | 
| `ai_translate()` | Global language support, content localization  | Multi-language customer support | Global customer support unification |
| `ai_summarize()` | Executive-level insights, content summarization | Condense long reports for management | 80% faster report generation for leadership |

#### Implementation Workflow
1. **Data Ingestion** → 2. **AI Processing** → 3. **Insights Generation**

---

## Domain-Driven Design Alignment

### Bounded Contexts & Data Products

| Bounded Context | Domain Data Product | Description |
|-----------------|---------------------|-------------|
| **Guest Experience** | `guest_feedback_enriched` | Enriched guest feedback with sentiment scores |
| **Operations** | `store_service_quality` | Store performance and service metrics |
| **Human Resources** | `employee_mentions_masked` | Employee feedback with PII protection |
| **Marketing** | `brand_sentiment_trends` | Brand perception tracking over time |


# Domain-Driven Data Architecture


## 📐 Bounded Contexts Implementation

| Ubiquitous Language | Domain (Bounded Context) | Domain Data Product | Description  | Owner | Business Capability |
|---------------------|--------|--------------|-------|-----------|---------------------|
| Guest Feedback | **Guest Experience** | `guest_feedback_enriched` | Enriched guest feedback with sentiment scores | CX Team | Customer Satisfaction |
| Service Quality | **Operations** | `store_service_quality` | Store performance and service metric| Ops Team | Service Excellence |
| Employee Feedback | **Human Resources** | `employee_mentions_masked` | Employee feedback with PII protection | HR Team | Employee Engagement |
| Brand Perception | **Marketing** | `brand_sentiment_trends` | Brand perception tracking over time | Marketing Team | Brand Management |

## 🎯 Key DDD Principles Applied

### 1. **Bounded Contexts**
Each domain has clear boundaries and owns its data products

### 2. **Ubiquitous Language**
Data products use business terminology, not technical jargon

### 3. **Aggregate Roots**
Delta tables serve as primary data aggregates for each domain

### 4. **Anti-Corruption Layer**
AI transformation layer translates raw data into domain models

# Domain-Driven Data Mesh Architecture

## Domain Data Products Matrix

| Business Domain | Bounded Context | Data Product | Schema | SLA |
|-----------------|-----------------|--------------|--------|-----|
| **Customer Experience** | Guest Interactions | `guest_feedback_enriched` | `guest_id`, `sentiment_score`, `feedback_category` | 99.9% |
| **Store Operations** | Service Delivery | `store_service_quality` | `store_id`, `service_score`, `wait_time`, `cleanliness` | 99.5% |
| **Human Resources** | Employee Engagement | `employee_mentions_masked` | `mention_id`, `department`, `sentiment`, `masked_text` | 99.9% |
| **Brand Management** | Marketing Analytics | `brand_sentiment_trends` | `date`, `channel`, `sentiment_trend`, `volume` | 99.0% |

## Implementation Example
```sql
-- Guest Experience Domain
CREATE TABLE guest_feedback_enriched (
    guest_id STRING,
    feedback_text STRING,
    sentiment_score DECIMAL(3,2),  -- from ai_analyze_sentiment()
    feedback_category STRING,      -- from ai_classify()
    mentioned_employees ARRAY<STRING>,  -- from ai_extract()
    created_at TIMESTAMP
) USING DELTA
COMMENT 'Domain: Guest Experience | Bounded Context: Feedback Management';
```

## DDD Architecture Principles
1. **Each domain owns its data products**
2. **Clear bounded contexts prevent ambiguity**
3. **Data products use business language**
4. **Domains are independently deployable**
5. **Inter-domain communication via contracts**











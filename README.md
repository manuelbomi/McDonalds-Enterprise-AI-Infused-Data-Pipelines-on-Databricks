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

#### <ins>1. Understand Content</ins>
Sentiment analysis, classification, summarization

#### <ins>2. Automate Governance</ins>
PII detection and masking using AI

#### <ins>3. Self-Adapt</ins>
Grammar correction, entity extraction, schema evolution

#### <ins>4. Globalize</ins>
Multilingual translation for global operations

> [!IMPORTANT]
> Please see Miscellaneous for snapshots of how AI functions are inserted on McDonald's customers' reviews data. Only the high level AI parts are shown in this project. Interested users (with .ipynb IDEs) can also download the reviews and codes for this repository and run it as stand-alone project without the Data Lake/Unity Catalog backends.
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

## Enterprise Data Ingestion Patterns


| Source Category | Data Source | Ingestion Method | Pattern | Example Code |
|-----------------|-------------|--------|---------|--------------|
| **Cloud Storage** | S3, ADLS, GCS | Auto Loader | Streaming | ```python<br>spark.readStream.format("cloudFiles")<br>``` |
| **Enterprise Systems** | SAP, Oracle, Salesforce | JDBC / Connectors | Batch | ```python<br>spark.read.jdbc(url, table)<br>``` |
| **Streaming Platforms** | Kafka, Event Hubs | Structured Streaming | Real-time | ```python<br>spark.readStream.format("kafka")<br>``` |
| **Mobile & Web Apps** | Custom Apps | REST APIs | Event-driven | Python `requests` library |
| **Third-Party Platforms** | External Services | APIs | Scheduled | Cron jobs / Airflow DAGs |







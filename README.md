# Data Engineer Assessment – FDA-Grade ETL Pipeline & Regulated Data Lake

This repository contains the full implementation supporting the Data Engineer
Assessment, including:

- Multi-source clinical ETL pipeline (CSV, JSON, HL7)
- Schema validation at every stage
- PHI redaction (regex + rule-based)
- Record-level provenance and integrity hashing
- Tiered regulated data lake architecture (Raw/Curated/QLM-Ready)
- Delta Lake versioning, time travel, and audit logs
- `/provenance` REST API (FastAPI)
- Deployment & compliance documentation

## Repository Structure

- `/code` – ETL pipeline source code  
- `/api` – FastAPI `/provenance` endpoint  
- `/docs` – Architecture, compliance, deployment documentation  
- `/samples` – Example logs, version history, sample data  
- `/config` – Schema definitions & redaction rules  
- `/DE_Assignment_Architecture.pdf` – Complete assessment

## How to Run ETL

1. Configure ADLS credentials in `pipeline_config.yaml`
2. Run `etl_pipeline.py` in Databricks or a Spark cluster
3. Outputs written to ADLS:  
   - Raw → Curated → QLM-Ready  
   - Provenance logs → `/audit/provenance`
   - Integrity hashes → `/integrity`

## How to Start API

API endpoint:

`GET /provenance/{record_id}`

## Compliance

- Fully aligned with HIPAA, FDA, and CFR Part 11  
- Complete lineage and reproducibility  
- Immutable audit logs (WORM)  
- PHI isolated and redacted before ML/QLM use  

## Contact
For any questions regarding this submission, feel free to reach out.


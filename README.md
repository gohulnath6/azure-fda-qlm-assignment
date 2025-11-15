# azure-fda-qlm-assignment

# Overview
This project implements a production-ready ETL pipeline and tiered data lake for a Quality Language Model (QLM) under FDA, HIPAA, and CFR Part 11 regulations.
It handles:
Multi-source data ingestion (CSV, JSON, HL7)
Schema validation at each stage
PHI redaction using formal rules
Provenance tracking for all transformations
SHA-256 integrity verification
Tiered Azure Data Lake storage (Raw → Curated → QLM-Ready)
Role-based access control (RBAC)
/provenance REST API

# Architecture
# ETL Pipeline

Ingest clinical data from multiple sources
Validate schema at every step
Scrub PHI using defined rules
Track provenance (timestamps, transformations, input/output hashes)
Compute integrity hashes (SHA-256)
Output QLM-ready dataset
Expose /provenance API for lineage tracking

# Tiered Data Lake

Raw Zone – Immutable, encrypted, exact copy of data
Curated Zone – Standardized, partially PHI-redacted, versioned (Delta Lake)
QLM-Ready Zone – Fully PHI-redacted, hashed, normalized datasets

# Azure Services Used

Azure Data Lake Storage Gen2 – Raw, Curated, QLM-ready zones
Azure Databricks – ETL processing, schema validation, PHI redaction
Azure App Service / Functions – Provenance API
Azure Monitor – Logging and audit
Delta Lake – Dataset versioning and time travel
Azure RBAC – Least privilege access control

# Compliance

HIPAA – PHI removal, RBAC, encryption
FDA – Data lineage, reproducible pipelines, integrity verification
CFR Part 11 – Timestamped, immutable audit logs
Security – Encryption, RBAC, network segmentation

# Deliverables

ETL pipeline scripts / notebooks
Delta Lake tables for tiered zones
Provenance API code
Architecture diagrams (physical + logical)
Compliance documentation

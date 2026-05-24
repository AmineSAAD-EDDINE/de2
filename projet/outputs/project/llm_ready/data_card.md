
# Data Card — Aviation LLM-Ready Dataset

| Field           | Value |
|-----------------|-------|
| Source          | OpenSky Network - ADS-B flight data |
| Track           | D — Aviation / OpenSky |
| Raw rows        | 1,000,000 |
| Curated rows    | 1,000,000 |
| Pass rate       | 100.00% |
| Schema version  | v1.0 |
| Intended use    | RAG / LLM fine-tuning for aviation domain |
| Filters applied | NULL removal, min_length=50, ascii_ratio≥0.95, xxhash64 dedup |
| Output format   | Parquet (snappy) |
| Output size     | 97.68 MB |
| Curated at      | 2026-05-24T19:42:26.757689 |

## Schema
- `doc_id`       STRING  — icao24_firstseen composite key
- `text`         STRING  — natural language flight description
- `dep_airport`  STRING  — ICAO departure airport code
- `arr_airport`  STRING  — ICAO arrival airport code
- `event_ts`     TIMESTAMP — flight start timestamp
- `source`       STRING  — dataset source identifier
- `version`      STRING  — schema version tag
- `curated_at`   TIMESTAMP — curation run timestamp
- `content_hash` LONG    — xxhash64 for deduplication

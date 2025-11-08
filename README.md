# Delta Lake With Polars

An example of how to read and write Delta Lake files using Polars.

*This example does not cover [deletion vectors](https://docs.databricks.com/aws/en/delta/deletion-vectors).*

- [About Polars](https://pola.rs/)
- [About Delta Lake](https://delta.io/)

#### Chapters

- Append Mode: Append New Row to Delta Table
- Overwrite Mode: Overwrite Delta Table with Filtered Data
- Merge Mode: Overwrite Delta Table with Filtered Data
  - ACTION - WHEN MATCHED UPDATE ALL
  - ACTION - WHEN_NOT_MATCHED_INSERT_ALL
  - ACTION - WHEN_NOT_MATCHED_BY_SOURCE_UPDATE
- Feature - Update data not in the source to UNKNOWN and UPSERT data from the source (update names for 1 & 4, add 10)

# Setup

```bash
uv sync
```

- Main Workspace: [main.ipynb](./main.ipynb)

## Data Structure

```
.
├── README.md
├── data
│   └── users.parquet # Source Parquet file
├── delta # Delta Lake directory
│   └── users # Delta Table
│       ├── _delta_log
│       ├── part-00000-....snappy.parquet
│       └── part-00000-....snappy.parquet
├── deltalake-with-polars.iml
├── main.ipynb
├── main.py
├── pyproject.toml
└── uv.lock
```

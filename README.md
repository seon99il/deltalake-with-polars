# Delta Lake With Polars

Polars를 이용하여 Delta Lake 파일을 읽고 쓰는 방법에 대한 예제입니다.

_[deletion vectors](https://docs.databricks.com/aws/en/delta/deletion-vectors)에 대해서는 다루고 있지 않습니다._ 

- [About Polars](https://pola.rs/)
- [About Delta Lake](https://delta.io/)

#### chapters

- Append Mode: Append New Row to Delta Table
- Overwrite Mode: Overwrite Delta Table with Filtered Data
- Merge Mode: Overwrite Delta Table with Filtered Data
  - ACTION - WHEN MATCHED UPDATE ALL
  - ACTION - WHEN_NOT_MATCHED_INSERT
  - ACTION - WHEN_NOT_MATCHED_BY_SOURCE_UPDATE
- Feature - Source에 없는 데이터는 UNKNOWN으로 업데이트하고, Source에만 있는 데이터는 UPSERT 하기 (1, 4이름 변경 및 10 추가)


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

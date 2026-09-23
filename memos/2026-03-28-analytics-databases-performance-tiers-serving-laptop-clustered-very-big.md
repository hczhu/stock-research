file-created-at:: 2026-03-28

# Analytics Database Performance Tiers (Serving, Laptop, Clustered, Very Big)

Source: user-provided screenshot titled `How do we think about performance`.

## Extracted Table

| Dimension | Serving | Laptop | Clustered | Very Big |
|---|---|---|---|---|
| Data Volume | `~100MB` | `1GB-50GB` | `100GB-10TB` | `10TB+` |
| Latency | `10s of ms @p999` | `100ms-low seconds` | `Seconds` | `Long` |
| Leader | `ClickHouse, SIEM tools` | `DuckDB` | `Snowflake, Databricks` | `Databricks` |
| Target vs DBR | `1000x @ the tail` | `10x p50+` | `3x p50` | `50%?` |

## Notes

- `DBR` is referenced directly in the slide text (`Target vs DBR`) and appears to be the comparison baseline.
- `50%?` in the `Very Big` column is shown with a question mark in the screenshot, indicating uncertainty or an approximate target.
- A red vertical line appears over part of the `Clustered` column in the image, but the text remains legible.

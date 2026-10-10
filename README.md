# etoro-taxdown-etl

Converts an eToro account statement (Spanish-language Excel) into the CSV template that [Taxdown](https://help.taxdown.es/es/articles/6108952-como-pasar-de-etoro-a-csv-taxdown) uses for the Spanish tax declaration.

It maps closed positions and dividends to Taxdown's fields (asset type, buy/sell, European vs non-European region via ISIN country code) and writes one `;`-separated CSV named after `tax_period` (rows are not filtered by year).

## Run

1. `pip install pandas numpy openpyxl datapackage`
2. Create `eToroPrivatePathsLib.py` next to the script (git-ignored) defining `etoro_excel_file`, `taxdown_template` and `taxdown_output_path` (paths; `taxdown_output_path` is a filename prefix, the script appends `<tax_period>.csv`).
3. Set `tax_period` in the script, then `python etoro_taxdown_etl.py`.

## Status

Personal script, last used for the 2021 tax year. Not maintained; check the Taxdown template format before reuse. No data is stored in this repo.

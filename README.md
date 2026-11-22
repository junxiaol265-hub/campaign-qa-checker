# Campaign QA Checker

An Excel portfolio demo for checking campaign and ad names and statuses against editable rules. It uses synthetic records and has formulas for 500 input rows.

[Download the Excel workbook](./campaign-qa-checker.xlsx?raw=true)

## How it works

- **Checks** accepts a record type, name, and status in columns A–C, rows 5–504.
- **Naming check** and **Status check** evaluate each record independently. Entirely empty rows show empty results.
- **Rules** lets you change prefixes, regions, suffixes, and statuses. Names follow `PREFIX-REGION-SUFFIX`. Matching is case-insensitive.

| Type | Name | Status | Naming check | Status check |
| --- | --- | --- | --- | --- |
| Campaign | CAM-US-SEARCH | ENABLED | PASS | PASS |
| Campaign | WRONG-US-SEARCH | ENABLED | FAIL | PASS |
| Ad | AD-GB-TEXT | DRAFT | PASS | FAIL |

## Verify the results

1. Change the Campaign prefix from `CAM` to `CMP`. The first result becomes `FAIL / PASS`. Then restore `CAM`.
2. Add `DRAFT` to **Rules!D8**. The third result becomes `PASS / PASS`. Then clear the added rule.
3. Enter `Ad`, `AD-GB-TEXT`, and `PAUSED` in **Checks!A504:C504**. The 500th record returns `PASS / PASS`. Clear it to restore empty results.

The exported workbook’s three sample rows were also recalculated in LibreOffice Calc.

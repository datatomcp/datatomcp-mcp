---
name: get-started
description: Connect a CSV or Google Sheet to datatomcp and ask the first question about it.
---

1. If the user has no dataset yet, tell them to sign in at https://app.datatomcp.com (free plan, no card) and add data under "Add data": upload a CSV, paste a CSV link, or pick a Google Sheet.
2. Call `list_datasets` to see what they have, then `describe_dataset` for the columns, types and today's date.
3. Before filtering a text column, call `distinct_values` to get the exact spelling (for example "France", not "FR").
4. Use `aggregate` for counts and totals, and `query_rows` to show specific rows.
5. Give the number, then say which dataset and version it came from.

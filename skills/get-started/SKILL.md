---
name: get-started
description: Ask the first question about the user's data in datatomcp (sheets, files, databases, Stripe, HubSpot, Airtable), as numbers, a chart or a dashboard.
---

1. Call `workspace_overview` first: it lists every dataset with what its columns mean, the team's approved definitions, the links between datasets and example questions with the exact call. A new account starts with `sample_sales` (example data): say so when you answer from it, and tell the user they can add their own data at https://app.datatomcp.com/app (files, Google Sheets, PostgreSQL, MySQL, Stripe, HubSpot, Airtable).
2. Use `describe_dataset` for example values, data quality and older versions.
3. Before filtering a text column, call `distinct_values` to get the exact spelling (for example "France", not "FR").
4. Use `aggregate` for counts and totals (with `{ metric: name }` when the team has approved a definition), and `query_rows` to show specific rows.
5. When a picture answers better (a trend, a ranking, a share), use `chart` with the same query and write the title as the takeaway.
6. Make a dashboard with `create_dashboard` only when the user asks for one; `refresh_dashboard` re-runs it on current data.
7. Give the number, say which dataset and version it came from, and share `meta.view_url` when the user wants to check it.

# Ustahub data: schema sheet

Ustahub is a local services marketplace that runs on quotes. Customers post service requests. The marketplace matches each request to professionals who cover that service and sends them the opportunity. A professional who opens the opportunity may pay a lead price to send a quote. A request collects quotes for 3 days, up to 4 quotes. The customer accepts at most one quote, and the request becomes a won job. Completed won jobs may receive a review.

All data is fictional and generated. Seven tables, supplied as CSV files and as a single DuckDB database.

The dataset holds about 3,419,031 rows in total. These files are not meant to be opened in a spreadsheet. Query the DuckDB database, or read the CSVs with a tool built for data this size.

A column of type boolean is written to the CSV files as the literal text True or False. Reading the DuckDB database gives a real boolean, and filtering on it works as expected. Reading a CSV file with a generic text reader instead gives the strings "True" and "False", and the string "False" is truthy, so a filter that treats the column as already boolean will silently keep every row. Convert the column explicitly before filtering on it if you are reading the CSV directly.

## customers

One row per customer account.
Rows: 373,619

| Column | Type | Meaning |
|---|---|---|
| customer_id | text |  |
| city | text |  |
| signup_date | date |  |

## pros

One row per professional account.
Rows: 7,000

| Column | Type | Meaning |
|---|---|---|
| pro_id | text |  |
| city | text |  |
| primary_service | text |  |
| joined_date | date |  |
| is_active | boolean |  |

## requests

One row per service request a customer posted.
Rows: 479,372

| Column | Type | Meaning |
|---|---|---|
| request_id | text |  |
| customer_id | text |  |
| category | text |  |
| service | text |  |
| city | text |  |
| created_at | timestamp |  |

## opportunities

One row per request and professional the request was matched to.
Rows: 1,775,209

| Column | Type | Meaning |
|---|---|---|
| opportunity_id | text |  |
| request_id | text |  |
| pro_id | text |  |
| sent_at | timestamp |  |
| notified | boolean | Whether the professional was sent a notification about the opportunity. |
| viewed | boolean | Whether the professional opened the opportunity. |
| viewed_at | timestamp, may be empty |  |

## quotes

One row per quote a professional sent on a request.
Rows: 629,244

| Column | Type | Meaning |
|---|---|---|
| quote_id | text |  |
| request_id | text |  |
| opportunity_id | text |  |
| pro_id | text |  |
| price | number | The price the professional quoted to the customer, in Turkish lira. |
| lead_price | number | What the professional paid the marketplace to send this quote, in Turkish lira. Set for each professional when they open the opportunity, so it can differ between quotes on the same request. |
| sent_at | timestamp |  |
| status | text | sent (the customer can still choose), accepted, or not_selected. |

## won_jobs

One row per request whose quote was accepted.
Rows: 109,138

| Column | Type | Meaning |
|---|---|---|
| won_job_id | text |  |
| request_id | text |  |
| quote_id | text |  |
| pro_id | text |  |
| scheduled_at | timestamp |  |
| completed_at | timestamp, may be empty |  |
| status | text | scheduled, completed or cancelled. |

## reviews

One row per review a customer left on a completed won job.
Rows: 45,449

| Column | Type | Meaning |
|---|---|---|
| review_id | text |  |
| won_job_id | text |  |
| rating | integer |  |
| tag | text |  |
| created_at | timestamp |  |

# Ustahub case: brief

## Your role

You are joining Ustahub as a product manager, in the squad that owns the Small Renovation category. Ustahub is a fictional local services marketplace that runs on quotes: customers post a request, professionals pay to send a quote, and the customer accepts at most one. Everything in this case, the company, the people and the data, is made up.

## The task

Deniz, a teammate in the squad, used an AI assistant to draft an analysis of a problem in Small Renovation and a recommendation. It is in the case notebook. Review it critically against the data, then write the squad lead a corrected recommendation that fits on one page.

The memo may contain errors. Treat each claim in it as something to check, not something to accept. Where the memo is right, say so. Where it is wrong, say what is true instead and how you know.

You do not need to identify every possible issue. Focus on the findings that materially change the product decision.

## Time

Plan on 120 to 180 minutes of work. Prioritize: a strong submission focuses on the few findings that materially change the decision rather than trying to cover everything. The deadline is in the email that sent you this brief.

A live session of 60 minutes follows. You walk us through your findings without slides, we work through a short SQL question together with AI allowed and your screen shared, and we talk about how you used AI. There is nothing else to prepare for it.

## Using AI

Use any AI tools you like, as much as you like. We do not require any particular tool or model. We read your AI conversations as part of your work, not against you.

We want to understand how you work with AI, not just the final output. Along with your submission, share the AI conversation or conversations that materially influenced your analysis or recommendation. You do not need to share every interaction, but the record should be representative of how you used AI for the case.

If your tool doesn't support share links, you can paste or export the relevant conversation. You may remove unrelated personal content.

In the live session, we may ask you to walk us through parts of your AI-assisted work: what you asked, what you accepted, what you challenged, and how you verified it.

## What you receive

The email that sent you this brief also carries a link to the case notebook. The notebook holds everything else you need, each in its own section:

- this brief;
- the memo, the draft you are reviewing;
- the schema sheet: what each of the seven tables holds and what its columns mean;
- the cells that load the data, seven tables in one DuckDB database;
- the submission checklist, a list to tick before you send.

## Working in the case notebook

The case notebook is a Google Colab notebook, shared with you read-only.

1. Open the link from the email and sign in with a Google account of your own.
2. Choose File, then Save a copy in Drive. Your copy lives in your own Drive, and we see it only when you send it to us.
3. In your copy, connect to a runtime, then Run all. The cells download the database, open a connection called `con`, and list each table with its row count. This takes under a minute.
4. Add your own cells in the section called Your work. Query with `con.sql("SELECT ...")`, and add `.df()` to see the result as a table.

If Colab restarts your session, run all the cells again. Your cells and their outputs stay in your copy.

Colab's own artificial intelligence features, such as the Gemini panel, send your prompts, the related code and the generated output to Google. Google keeps them for up to 18 months, and people at Google may read and annotate them to improve its products. The case data is fictional, so nothing confidential is at risk, but your own work enters Google's pipeline because we asked you to work there. You may use Colab's AI features, use other tools alongside Colab, or not use Colab at all.

## If you prefer not to use a Google account

Reply to the email that sent you this brief and ask for the offline pack. It holds the same material: this brief, the memo, the schema sheet, the checklist, the seven CSV files, the DuckDB database, and the case notebook, which runs in Jupyter or any editor that runs notebooks and opens the database from the same folder. To run it you need Python 3 with Jupyter, or an editor such as VS Code, and an internet connection for the first cell, which installs DuckDB. Choosing the offline pack makes no difference to how we assess your work.

## The one-pager

One page, with these five sections:

1. What you agree with in the memo.
2. What you corrected, and how you know.
3. Your recommendation: what you would do now, what you would not do yet, and why.
4. Assumptions and open questions.
5. What you would do next with one week.

## What to send

Reply to the email that sent you this brief, before the deadline in it, with:

- The one-pager, as a PDF.
- Your notebook, as a file. In Colab choose File, then Download, then Download .ipynb. Run all the cells once before you download, so the outputs are in the file.
- The AI conversation or conversations that materially influenced your work, as share links, exported text or pasted transcript. You do not need to share every interaction, but what you share should be representative of how you used AI for the case. If you use a tool such as Colab's Gemini panel that does not preserve the conversation for you, copy the relevant exchanges as you go.

## Your data

Your one-pager, your notebook and your AI conversations are personal data under KVKK and GDPR. We keep them in our hiring system with the rest of your application, and delete them on the same schedule. People assess your work; no AI scores it.

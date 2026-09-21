# n8n course syllabus (study notes)

Summary of course blocks. Not a verbatim transcript.
Practice happens in the n8n editor, not in these files.

## Structure of a workflow

Trigger → Action → data transform → core/logic → optional AI.

Do not memorize every node. Pick by job.

## Triggers

Manual, Form, Telegram, Schedule, Webhook, Gmail, Workflow Trigger, Airtable, Chat.

Webhook = external app pushes an event to an n8n URL (reverse of polling).
Workflow Trigger = split a large automation so one failure does not take down everything.

## Actions

Gmail (get / label / send), Notion CRUD, Google Sheets (append / update / lookup / clear).

OAuth (minimum for this course track):

- Sheets append: `https://www.googleapis.com/auth/spreadsheets`
- Gmail send: `https://www.googleapis.com/auth/gmail.send`

## Logic

| Node | Role |
| --- | --- |
| IF | two branches, true / false |
| Switch | many routes + fallback |
| Filter | keep vs discard items on one path |

AND = all conditions. OR = any condition.

## Data transform

| Node | Role |
| --- | --- |
| Edit Fields (Set) | add or change fields |
| Rename Keys | rename keys only |
| Date & Time | timezones, add days, format |
| Merge | join streams |
| Aggregate | totals / summaries |
| Split Out | explode a list into items |
| Code | JavaScript (low-code) |

Expression = dynamic value from previous item (`{{ $json.name }}`). Fixed = hardcoded.
Clean data first. Messy data makes messy workflows.

HTTP Request = you pull an API (GET/POST/PUT/PATCH/DELETE).
Webhook = they push to you.

## AI nodes (overview)

AI Agent, Basic LLM Chain, Sentiment, Q&A chain, Text classifier, Hugging Face embeddings (semantic search).

## Example scenarios (course)

1. AI lead scoring: form → LLM hot/cold → store → email hot leads → notify sales.
2. Creator distribution: Drive file → YouTube / LinkedIn / X / Telegram / Notion.
3. E-commerce: order → stock → invoice → warehouse → WhatsApp → optional Sheets.
4. Support agent: message → intent → auto-reply or human escalate.

UNVERIFIED from course marketing: “70–80% support load reduction”.

## Sample workflows in this repo

See `workflows/`. JSON has no `credentials` blocks. Sheet IDs are placeholders. Import in the editor and attach your own OAuth.

## Architecture pointer

See `docs/research/2026-09-21-n8n-docker-oauth.md` for n8n 2.39.8 / Docker / OAuth facts.

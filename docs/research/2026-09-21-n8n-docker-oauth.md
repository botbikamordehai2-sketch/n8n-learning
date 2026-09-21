# 2026-09-21 — n8n, Docker Desktop, OAuth

## FACT

- n8n **stable**: 2.39.8 (2026-09-18). **beta**: 2.40.3.
- התקנה רשמית: npm, Docker, Docker Compose, one-line setup. אפליקציית Desktop הופסקה (ריפו בארכיון).
- npm דורש Node.js 20.19–24.x; מ-n8n 3.0 (מתוכנן אוקטובר 2026) npm מסומן deprecated.
- Docker Desktop + WSL2 ב-Windows: וירטואליזציה ב-BIOS, WSL 2.1.5+, Windows 11 23H2+. דרישת RAM רשמית ל-WSL2: 8GB.
- Sheets append: `https://www.googleapis.com/auth/spreadsheets` (או `drive` / `drive.file`).
- Gmail send בלבד: `https://www.googleapis.com/auth/gmail.send` (Sensitive).

## OBSERVATION

- ב-Windows עדיף Docker + volume על npm גלובלי.
- credential רשמי של Gmail ב-n8n עלול לבקש scopes רחבים יותר מ-`gmail.send`.

## UNVERIFIED

- האם Windows 11 Home נכלל במדויק בטבלת Docker Docs הנוכחית במחשב היעד.

אין סודות בקובץ הזה.

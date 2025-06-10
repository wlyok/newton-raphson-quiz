# Newton-Raphson Quiz System — Quiz #3

This project provides a complete interactive quiz web interface for students to solve a **fourth-degree polynomial** using the **Newton-Raphson method**. Each student gets a randomly generated problem with guaranteed real roots.

## 🔧 Features

- Students log in with **ID and password**
- Each quiz instance uses a **different randomized equation**
- Four roots must be submitted, with live feedback per answer
- Students paste their **Python code** for review
- Submissions are recorded in a linked **Google Sheet**
- Sheet also stores code, scores, and logs for each attempt
- Buttons have **5-second cooldowns** to prevent server overload
- Students can **retry until all answers are correct** within the time limit

---

## 📁 File Structure

| File / Sheet | Purpose |
|--------------|---------|
| `index.html` | Front-end quiz interface for students |
| `google_apps_script.js` | Google Apps Script backend |
| `Python_Quiz_Scores_2025_F.xlsx` | Google Sheet template with 17 worksheets |

---

## 🗂 Google Sheet Setup

Make a copy of the `Python_Quiz_Scores_2025_F.xlsx` and upload it to Google Sheets. It must contain the following sheets:

- `STUDENT_LIST` — Names + IDs
- `RECORD 01` to `RECORD 14` — One for each quiz log
- `FINAL_SCORES` — Final score table (one row per student)
- `CODES` — Transposed structure: Names in row 1, IDs in row 2, code versions per student per quiz

---

## 🚀 Setup Instructions

### 1. **Deploy Google Apps Script**

- Open Google Sheets
- Extensions → Apps Script
- Paste `google_apps_script.js`
- Update:
  ```javascript
  const CURRENT_QUIZ_NUMBER = 3;
  const QUIZ_PASSWORD = '*';

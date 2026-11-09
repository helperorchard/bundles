
    __( O)>  ● new session · openrouter openrouter/free
   \____)    20261109_23 · /workspace/skill-bundles
     L L     goose is ready
# SOP: Export Stripe Payouts → Update Running Totals → Email Dylan (or Slack if login fails)

**Task:** Export last week’s Stripe payouts CSV to the Finance Drive folder, update the Running Totals sheet, and email Dylan a one‑line total (or Slack him if Stripe login fails).  

---

## Before‑you‑start
- **Logins** (from password manager):  
  - Stripe account (email/username & password)  
  - Google account (for Drive & Sheets)  
  - Email client (e.g., Gmail)  
  - Slack account  
- **Tools**: Web browser, Google Drive, Google Sheets, Email app, Slack client.  
- **Files**:  
  - Finance Drive folder **“Payouts”** (location: `Finance Drive > Payouts`).  
  - **Running Totals** Google Sheet (name may vary; locate in the same Drive).  

---

## Standard Operating Procedure
1. **Open browser** and navigate to the Stripe login page.  
   *Why:* To access the payouts data.  
2. **Log in to Stripe** using credentials from the password manager.  
   *Check:* Dashboard loads successfully; you see the “Payments” menu.  
3. In Stripe, go to **Payments → Payouts**.  
   *Why:* To locate the CSV export for the last week.  
4. Click **Export CSV** and **save directly to Google Drive** → select the **Finance Drive > Payouts** folder (do not download to the local desktop).  
   *Check:* The CSV file appears in the Drive folder without a local copy.  
5. **Open the Running Totals Google Sheet** from Drive.  
   *Why:* To add the weekly totals.  
6. **Add a new row** in the sheet:  
   - Column A – start date of the week (e.g., `2026-11-04`).  
   - Column B – total payout amount (sum of the “amount” column in the CSV).  
   - Column C – total fees (sum of the “fee” column in the CSV).  
   *Check:* Row contains three values, date formatted as `YYYY‑MM‑DD`, no duplicate rows.  
7. **Save the sheet** (auto‑saved in Drive).  
   *Why:* To persist the updates.  
8. **Compose an email** to Dylan:  
   - Subject: `Weekly Stripe Payout Total`  
   - Body (one line): `Total payout for week of [date]: $X,XXX.XX` (replace with actual total).  
   *Check:* Email includes correct date and amount, no extra text.  
9. **Send the email** via your email client.  
   *Check:* Sent folder shows the message; no sending errors.  
10. **If Stripe login fails** at step 2, open Slack and **ping Dylan** (e.g., “Stripe login failed – need assistance”).  
    *Check:* Slack message is sent to Dylan (or the appropriate channel/user).  

---

## Checks (post‑step verification)
- **Step 4:** Confirm the CSV file is in the correct Drive folder and not on the local desktop.  
- **Step 6:** Verify the three columns contain the correct sums and the row is not duplicated.  
- **Step 9:** Ensure the email was sent and matches the one‑line format.  

---

## Gaps (questions for the owner)
- What exact date format does Column A require (e.g., `YYYY‑MM‑DD` vs. `MM/DD/YYYY`)?  
- What is the precise name and location of the Running Totals sheet (file name, tab name)?  
- Which Slack channel or user handle should be used to ping Dylan?  
- Should the total amount and fees be summed automatically in the sheet, or are they manually entered?  
- Is the email to be sent automatically (e.g., via a script) or manually by the VA?  

---  

*Prepared for a new VA who can use a browser and email.*

Loading recipe: SOP Writer
Description: Turns a messy description of how you do a task into a numbered step-by-step procedure someone new could follow.


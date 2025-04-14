# 🧾 Invoice Due Reminder

Automate client payment reminders with ease!  
This Power Automate flow checks a **SharePoint List or Excel Sheet** for upcoming invoice due dates and automatically sends reminder emails to clients both **3 days before the due date** and **on the due date**.

---

## 💡 Features

- 🔄 Scheduled automation (daily or as configured).
- 📆 Sends reminder emails:
   - **3 days before the invoice due date**.
   - **On the exact due date**.
- 📤 Customizable email templates.
- 💾 Works with both SharePoint Lists and Excel Tables (stored in OneDrive or SharePoint).
- ⚡ No manual follow-up — fully automated!

---

## 🏗️ Flow Overview

| Step                | Purpose                                      |
|----------------------|----------------------------------------------|
| Recurrence Trigger   | Runs on a schedule (usually daily).         |
| Get Items            | Fetches all invoices from SharePoint/Excel. |
| Apply to Each        | Loops through each invoice record.          |
| Compose (DueDate)    | Extracts the `DueDate` from each item.       |
| Condition            | Checks if due date is today or 3 days away. |
| Send Email (Outlook) | Sends reminder email to the client.         |

---

## 📊 Data Source Structure

Your **SharePoint List** or **Excel Table** should have at least:

| Column Name      | Purpose                         |
|------------------|---------------------------------|
| `ClientEmail`    | Client's email address.         |
| `DueDate`        | Invoice due date (Date type).   |
| `InvoiceNumber`  | Invoice identifier (optional).  |

---

## ⚙️ How to Deploy

1. Download `FlowPackage.zip` from this repo.
2. Go to [Power Automate](https://make.powerautomate.com) → **My flows** → **Import**.
3. Upload the `.zip` file.
4. During import, configure:
    - SharePoint/Excel connection.
    - Outlook connection for sending emails.
5. Save and **Test the flow**.

---

## 💌 Sample Email Templates

> **Subject:** Friendly Reminder: Invoice Due on {{DueDate}}  
> **Body:**  
> Hi [Client Name],  
> This is a reminder that your invoice **#[InvoiceNumber]** is due on **{{DueDate}}**. Kindly process the payment at your earliest convenience.  
> Thank you!

---

## 💡 Customization

- Edit the email body in the **Send Email** action.
- Adjust the condition logic to send reminders at different intervals (e.g., 7 days before, 1 day before).
- Integrate Teams notifications, SMS, or other channels if needed.

---

## 🤝 Contributions

Feel free to fork, customize, and improve the flow logic.  
Pull Requests are welcome!

---

## 🧠 Author

Created by **Nandan Vallamdasu**
If you find this useful — ⭐ star the repo!

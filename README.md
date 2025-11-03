# 🚀 Automated Order & Inventory Management System (Plumbing Business)

This project automates the **entire order-to-restock workflow** for a small business using **Google Sheets, HTML, Gmail, and Google Forms** — no ERP or paid tools required.  

---

## 💡 Overview

When a **customer places an order** through the plumbing website, the system automatically:
1. Adds the order details into **Google Sheets**.
2. Updates inventory levels in real time using formulas.
3. Triggers **auto reorder emails** to vendors when stock hits the restock threshold.
4. Collects vendor responses through a **Google Form**.
5. Updates the **expected restock date** automatically in the same sheet.

The result:  
⚙️ 100% automation — from customer order → inventory update → vendor restock confirmation.

---

## ⚙️ Workflow

**Step 1:** Customer places an order via `index.html` form.  
**Step 2:** Data sent to **Google Apps Script (appscript.gs)**.  
**Step 3:** Script writes order details into Google Sheets.  
**Step 4:** Google Sheets formulas auto-calculate stock and reorder status.  
**Step 5:** Gmail automation sends reorder email with Google Form link to vendor.  
**Step 6:** Vendor fills the form, and the sheet auto-updates with the restock date.

---

## 🧠 Tech Stack

| Technology | Purpose |
|-------------|----------|
| **HTML + JS** | Customer order interface |
| **Google Sheets** | Inventory database + formulas |
| **Google Apps Script** | Backend automation |
| **Gmail API** | Auto email notifications |
| **Google Forms** | Vendor confirmation |
| **Google Workspace Automation** | Real-time triggers and updates |

---

## 🧾 Key Formulas

```excel
# Current Stock
=ARRAYFORMULA(B2:B - D2:D)

# Reorder Trigger
=IF(E2 <= F2, "REORDER", "OK")

# Expected Restock Date
=IF(G2="REORDER", VLOOKUP(A2, Vendor_Form!A:C, 3, FALSE), "")

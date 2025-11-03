# 🚀 Smart Order & Inventory Automation System

An intelligent, end-to-end **Order and Inventory Management System** built for a **plumbing business**, fully powered by **Google Sheets, Gmail, Google Forms, HTML**, and **n8n automation workflow**.

This project automates everything — from **customer orders to vendor restocks** — using Google Workspace tools and no expensive ERP software.

---

## 🧩 Overview

When a customer places an order on the website, the system automatically:

1. Logs the order into **Google Sheets**.  
2. Updates stock quantity in real time using formulas.  
3. Checks the **restock threshold** and triggers a reorder if needed.  
4. Sends an **automatic email to the vendor** requesting new stock.  
5. The vendor receives a **Google Form** to confirm delivery details.  
6. Once submitted, the **restock date** updates automatically in the sheet.  

✅ 100% automation — no manual tracking, no missed reorders.

---

## ⚙️ System Workflow

Below is the workflow automation built in **n8n**, integrating Google Sheets, Gmail, AI, and conditional logic for smart decision-making:

![Smart Order & Inventory Automation System](main/N8N%20Workflow%20Smart%20Order%20%26%20Inventory%20Automation%20System.png)

---

## 🎬 Demo Video

🎥 **Watch Full Project in Action:**  
[▶️ Click Here to View Demo on Google Drive](https://drive.google.com/file/d/12VM9dR3X4_2E6tWzH-CtY2XsaE-dvfp8/view?usp=sharing)

*(The demo showcases the entire loop — customer order → stock update → reorder email → vendor form → restock confirmation.)*

---

## 🧠 Tech Stack

| Technology | Purpose |
|-------------|----------|
| **HTML + JS** | Customer order form (frontend) |
| **Google Sheets** | Inventory database + formulas |
| **Google Apps Script** | Backend automation logic |
| **Gmail API** | Automated reorder emails |
| **Google Forms** | Vendor restock confirmation |
| **n8n Automation** | Workflow orchestration |
| **OpenAI LLM** | Smart decision logic integration |

---

## 🧾 Key Google Sheets Formulas

```excel
# Auto stock update
=ARRAYFORMULA(Initial_Stock - SUMIF(OrderRange, ItemName, QuantityRange))

# Restock alert
=IF(Current_Stock <= Restock_Level, "REORDER", "OK")

# Expected restock date from vendor form
=IF(G2="REORDER", VLOOKUP(A2, Vendor_Form!A:C, 3, FALSE), "")

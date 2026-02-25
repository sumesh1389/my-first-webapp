# NTG Infotech Business Management System — Project Context

## Company Details
- Company Name: NTG Infotech Pvt. Ltd.
- Working Location: Gwalior, Madhya Pradesh
- Registered: Faridabad
- Services: Website Development, Social Media Management, Digital Marketing
- Owner is building this system personally as a beginner developer

## What This System Is
A complete business management and accounting ledger system for tracking
clients, work contracts, quotations, invoices, payments, and credit notes.
The system must be highly advanced yet easy to use by a normal person.
UI must be modern, attractive, eye-catching, and professional — like a
premium SaaS product.

## Core Business Logic (Very Important)

### Two Types of Services
1. One-Time Project (e.g. Website Development) — fixed total amount,
   paid in 2-3 installments
2. Monthly Recurring (e.g. Social Media Management, Digital Marketing)
   — fixed monthly rate, invoice raised every month

### Client Structure
- One client is created once and never duplicated
- A client can have multiple contracts at any time
- New work = new contract under same client

### Complete Business Flow
Quotation → Contract → Proforma Invoice (optional) → Tax Invoice → Payment
                                                                        ↓
                                                              Credit Note
                                                          (if client doesn't pay
                                                           and GST needs reversal)

### Quotation Logic
- Status: Draft → Sent → Accepted / Rejected / Negotiating
- Client can negotiate — quotation can be edited
- On acceptance → converts to Contract with one click

### Invoice Logic
- Proforma Invoice is optional — used for uncertain/new clients
- Proforma is NOT a GST document — no GST liability triggered
- On payment received → converts to Tax Invoice with one click
- Tax Invoice IS a GST document — GST liability triggered on creation
- Invoice statuses: Unpaid / Partially Paid / Paid / Overdue / Written Off
- Payments recorded separately against invoice
- Invoice status updates automatically based on payments received

### Credit Note Logic
- Raised against a Tax Invoice when client doesn't pay
- Reverses GST liability so owner doesn't pay tax on unreceived money
- Must be issued within same financial year or by September of next FY
- Has reason field and is linked to original invoice

### Bad Debt
- If client runs away permanently, invoice can be marked Written Off
- Record stays in system forever for reference and legal proof
- Moves out of active pending so dashboard numbers stay clean

### Payment Recording
- Amount, date, payment mode: UPI / NEFT / Cash / Cheque
- UTR / reference number field
- Partial payments supported — multiple payments against one invoice

## Modules
1. Dashboard
2. Clients
3. Quotations
4. Contracts
5. Proforma Invoices
6. Tax Invoices
7. Payments
8. Credit Notes

## Dashboard Should Show
- Total revenue received this month and this year
- Total outstanding across all clients
- Overdue invoices list
- Recent payments
- Top clients by value
- Charts for revenue trends

## Tech Stack
- Frontend: React.js + Tailwind CSS + Shadcn/ui + React Router + Axios + Recharts
- Backend: Node.js + Express.js + Mongoose
- Database: MongoDB Atlas (cloud hosted)
- Auth: JWT (login system)
- Print: React PDF / Print CSS for invoices and quotations

## Folder Structure
my-web-app/
├── client/              → React frontend
│   └── src/
│       ├── components/  → Reusable UI pieces
│       ├── pages/       → Full screens
│       ├── services/    → API call functions
│       └── App.jsx
├── server/              → Node.js backend
│   ├── models/          → MongoDB schemas
│   ├── routes/          → API endpoints
│   ├── controllers/     → Business logic
│   ├── middleware/       → Auth, error handling
│   └── server.js
├── .env
├── .gitignore
└── README.md

## Build Order
1. Project folder structure setup + dependency installation
2. MongoDB Atlas setup + backend server connection
3. Clients module — backend API + frontend UI
4. Quotations module
5. Contracts module
6. Proforma Invoice module
7. Tax Invoice module
8. Payments module
9. Credit Notes module
10. Dashboard with charts
11. Printable views for Quotation and Invoice

## Developer Notes
- Developer is a complete beginner — explain every step clearly
- Give exact terminal commands to run
- Build one module at a time — fully working before moving to next
- UI must look premium, modern, eye-catching at every stage
- System should be understandable even when opened after 2 years
- Every decision made in this system has a business reason behind it
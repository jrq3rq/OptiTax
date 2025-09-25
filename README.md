# Overview

OptiTax is a privacy-first, React-based web application built with Create React App, designed to guide small to medium enterprises (SMEs) and high-net-worth individuals through an 18-question **Tax Cycle Optimizer v4 Questionnaire**. It streamlines a tax-efficient profit transfer and borrowing strategy, ensuring compliance with US tax laws (e.g., IRC Secs. 243, 385, 168, 61, 163, 542, 7701(o), 1014).

The chatbot processes inputs in-memory with no data storage, generating a **client-side PDF report** containing:
- Tax savings
- Compliance checklist
- Risk warnings
- CPA referral
- Audit trail

---

# Objective

Enable users to:

- **Form Entities**: Establish C-corp holding company (Holdco) owning ≥80% of operating company (Opco) for tax-free dividends via Dividends Received Deduction (DRD, IRC Sec. 243).
- **Transfer Profits**: Move Opco profits to Holdco, avoiding double taxation.
- **Purchase Assets**: Holdco acquires appreciating assets (e.g., real estate, securities) with deductions (IRC Sec. 168).
- **Borrow**: Secure non-taxable loans (e.g., HELOCs, margin loans; IRC Sec. 61) against assets, with deductible interest (IRC Sec. 163).
- **Ensure Compliance**: Avoid Personal Holding Company (PHC) status (IRC Sec. 542), Unrelated Business Taxable Income (UBTI), and ensure economic substance (IRC Sec. 7701(o)).
- **Plan Exit**: Document assets for stepped-up basis at death (IRC Sec. 1014).
- **Audit**: Provide audit-ready reports and CPA referrals.

---

# Features

- **Questionnaire**: 18 conversational questions covering entity setup, profit transfer, asset purchase, borrowing, compliance, and planning.
- **Privacy**: In-memory processing (React state), no data storage, cleared post-session via `clearSession.js`, SOC 2-compliant.
- **Report**: Client-side PDF (jsPDF) with tax savings, compliance checklist (e.g., Form 1120), risk warnings (e.g., PHC, high debt-to-asset ratio), CPA referral, and audit trail.
- **Entity Support**: C-corp, S-corp, LLC, partnership, hybrid; validates DRD eligibility and multi-entity coordination.
- **Input Validation**: Checks numeric inputs (e.g., revenue, loan amounts), flags compliance risks (e.g., IRC Sec. 385 debt-equity issues).
- **Accessibility**: Novice-friendly with examples (e.g., “E-commerce” for business activity) and glossary for tax terms (e.g., “DRD: Tax-free dividends”).
- **Minimal Design**: Barebones dependencies (React, jsPDF), no external APIs (e.g., Yahoo Finance, QuickBooks).
- **Single-Session**: Completion required in one session due to no data retention.


## Project Structure

```markdown
├── public/ # Static assets
│   ├── favicon.ico # Browser tab icon
│   ├── index.html # Root HTML
│   └── manifest.json # Basic PWA manifest
├── src/ # Frontend source code
│   ├── components/ # Reusable components
│   │   ├── OptiTaxChatbot.js # Core chatbot logic
│   │   └── QuestionRenderer.js # Renders question types
│   ├── core/ # Core utilities
│   │   └── reportGenerator.js # Client-side PDF generation
│   ├── styles/ # CSS
│   │   ├── OptiTaxChatbot.css # Chatbot styles
│   │   └── global.css # Minimal app-wide styles
│   ├── App.js # Main app layout
│   ├── index.js # App entry point
│   └── index.css # Global CSS (resets)
├── .gitignore # Ignores node_modules, build
├── package.json # Dependencies (react, jsPDF)
└── README.md # Basic setup guide
```

Financial Governance & Stakeholder Banking Layer
Project Phase: 02 - Resource Management
Model: Multi-Stakeholder Grant & Dividend Distribution
1. The "Joint Dealing" Framework
To ensure sustainability, the Lefa-Bot project utilizes a Special Purpose Vehicle (SPV) to manage funds from government grants (TIA/DSI) and private investors. This layer ensures that even stakeholders without traditional bank accounts (e.g., rural farmers) can receive payments via Smartphone Proxy IDs.
2. SQL Banking Schema (The Audit Trail)
This database structure tracks every cent from the initial R65,000 Pilot Grant to final export dividends.
sql
-- Track Stakeholders & Payment Proxies
CREATE TABLE banking_registry (
    stakeholder_id INT PRIMARY KEY,
    entity_name VARCHAR(100),
    role ENUM('Farmer', 'IKS_Expert', 'Academic', 'Investor'),
    payment_proxy_id VARCHAR(50) -- e.g., Mobile Money/E-wallet ID
);

-- Audit Trail for Grant Disbursements
CREATE TABLE grant_ledger (
    transaction_id INT PRIMARY KEY AUTO_INCREMENT,
    timestamp DATETIME DEFAULT CURRENT_TIMESTAMP,
    source_fund VARCHAR(100), -- e.g., 'TIA Seed Capital'
    amount_zar DECIMAL(15, 2),
    purpose VARCHAR(255) -- e.g., 'IoT Hardware Procurement'
);
Use code with caution.

3. Revenue Sharing Model
The "Lefa-Bot" economy is designed for Equity:
40% Operational Reinvestment: Maintenance of sensors and cloud servers.
30% Farmer Dividends: Direct profit from the sale of compliant hemp fibre.
20% IKS Royalty: Payments to Sangoma collectives for the use of patented traditional knowledge.
10% Academic R&D: Funding for continuous validation by University partners.
4. Scalability to Eswatini (The Lilangeni Factor)
This financial layer is designed to be Currency-Agnostic. By switching the currency code from ZAR to SZL (Lilangeni), the same audit logic can be used by the Eswatini Agricultural Development Fund to manage national hemp subsidies.
---
**📜 Project Status & Disclaimer**

**This repository represents a Conceptual Framework and Technical Proposal developed as a Capstone project for the Google Data Analytics Professional Certificate. While the architectural designs, SQL schemas, and Python logic are functional prototypes, the stakeholder engagements and financial forecasts are proposed models intended for future implementation.**

**Co-Innovation Notice: This project was developed through an iterative, high-level collaboration between the author and Google Gemini (AI). This partnership was utilized to refine technical specifications, ensure regulatory alignment, and structure the data for global scalability.**

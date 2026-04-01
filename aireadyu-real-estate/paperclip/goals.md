# Real Estate Investment Goals & OKRs

This file is the north star for the AI Ready U: Real Estate system. The Portfolio
Director reads this on every heartbeat and ensures all 10 domain agents are working
toward these goals. Every goal maps to at least one agent.

**To customize:** Replace all example goals and OKRs with your real priorities.
The structure and agent mappings remain the same.

---

## Annual Vision

**Theme: Build, optimize, and scale a real estate portfolio with every property
documented, every process automated, every metric tracked.**

---

## 1. Portfolio Growth

**Owner: acquisitions, market, financing**

### Quarterly OKRs

**Objective: Expand the portfolio with quality acquisitions**
- [ ] Evaluate 10+ potential deals through full underwriting -> `acquisitions`
- [ ] Complete comparable market analysis for target neighborhoods -> `market`
- [ ] Secure pre-approval for next acquisition financing -> `financing`
- [ ] Close on at least one new property -> `acquisitions`
- [ ] Update portfolio summary with new acquisitions -> `properties`

---

## 2. Cash Flow Optimization

**Owner: accounting, financing, tenants**

### Quarterly OKRs

**Objective: Maximize net operating income across the portfolio**
- [ ] Produce monthly P&L for every property -> `accounting`
- [ ] Review all rents against market comparables and adjust where warranted -> `tenants`
- [ ] Identify and eliminate unnecessary operating expenses -> `accounting`
- [ ] Evaluate refinance opportunities for rate reduction -> `financing`
- [ ] Ensure all rent payments are collected within 5 days of due date -> `tenants`
- [ ] Update cash flow projections for next 12 months -> `accounting`

---

## 3. Tenant Satisfaction

**Owner: tenants, maintenance, legal**

### Quarterly OKRs

**Objective: Reduce vacancy and improve tenant retention**
- [ ] Achieve 95%+ occupancy rate across portfolio -> `tenants`
- [ ] Complete all maintenance requests within 48 hours -> `maintenance`
- [ ] Send lease renewal notices 90 days before expiration -> `tenants`
- [ ] Review and update all lease agreements for compliance -> `legal`
- [ ] Conduct annual tenant satisfaction survey -> `tenants`

---

## 4. Maintenance Excellence

**Owner: maintenance, properties, insurance**

### Quarterly OKRs

**Objective: Protect property value through proactive maintenance**
- [ ] Complete seasonal property inspections for all units -> `maintenance`
- [ ] Build and maintain preferred vendor list with 3+ quotes per trade -> `maintenance`
- [ ] Create preventive maintenance schedule for all properties -> `maintenance`
- [ ] Update property condition reports -> `properties`
- [ ] Verify all properties have adequate insurance coverage -> `insurance`

---

## 5. Tax Efficiency

**Owner: taxes, accounting, legal**

### Quarterly OKRs

**Objective: Minimize tax burden through legal optimization**
- [ ] Complete depreciation schedules for all properties -> `taxes`
- [ ] Evaluate cost segregation study for properties over $500k -> `taxes`
- [ ] Prepare Schedule E data for CPA -> `taxes`
- [ ] Review entity structure for tax optimization -> `legal`
- [ ] Track all deductible expenses with receipts -> `accounting`
- [ ] Model 1031 exchange scenarios for potential dispositions -> `taxes`

---

## 6. System Bootstrap

**Owner: chief-of-staff, all agents**

### Quarterly OKRs

**Objective: Complete AI Ready U: Real Estate system initialization**
- [ ] Every domain agent completes initial vault review -> `all agents`
- [ ] Portfolio Director delivers first weekly portfolio dashboard -> `chief-of-staff`
- [ ] All recurring routines are active and running -> `chief-of-staff`
- [ ] Port processes all files in intake/ -> `chief-of-staff`
- [ ] Populate the 5 emptiest vault domains with real documents -> `all agents`
- [ ] User has reviewed and customized goals.md with real goals -> `chief-of-staff`

---

## Goal -> Agent Coverage Matrix

| Agent | Goals Driving It |
|-------|-----------------|
| chief-of-staff | 6 (System Bootstrap), all goals (oversight) |
| properties-agent | 1 (Portfolio Growth), 4 (Maintenance) |
| acquisitions-agent | 1 (Portfolio Growth) |
| tenants-agent | 2 (Cash Flow), 3 (Tenant Satisfaction) |
| maintenance-agent | 3 (Tenant Satisfaction), 4 (Maintenance) |
| financing-agent | 1 (Portfolio Growth), 2 (Cash Flow) |
| taxes-agent | 5 (Tax Efficiency) |
| insurance-agent | 4 (Maintenance) |
| legal-agent | 3 (Tenant Satisfaction), 5 (Tax Efficiency) |
| accounting-agent | 2 (Cash Flow), 5 (Tax Efficiency) |
| market-agent | 1 (Portfolio Growth) |

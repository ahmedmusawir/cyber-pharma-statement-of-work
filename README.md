# Cyber Pharma SOW (Statement of Work)

## Pharmacy Reimbursement Audit Web Application

**Client:** Frank Tant, CP Health Clinics  
**Developer:** Cyberize Group  
**Project Lead:** Mical Johnson  
**Date:** August 8, 2025  
**Project Duration:** 7 weeks  
**Target Launch:** October 1, 2025

---

## Project Overview

Cyberize Group will develop a HIPAA-compliant custom SaaS web application that enables independent pharmacies to evaluate whether commercial reimbursements meet Alabama Medicaid minimums, generate appeals, and automate the submission of reimbursement discrepancy reports to Pharmacy Benefit Managers (PBMs) and/or regulatory agencies. The application will transform the client's existing Python desktop prototype into a scalable, multi-tenant web platform optimized for Alabama's new Medicaid minimum payment requirements.

---

## Scope of Work

### What We Will Deliver

**1. User & Data Management**

* Secure user registration and login via Supabase Auth.
* Multi-tenant access — each pharmacy can only see its own data.
* One user role for MVP: **Pharmacy Admin** (full access to upload data, manage rates, generate reports).
* Basic audit trail of sign-ins, file uploads, and report generation.

**2. Data Import**

* Manual upload of claims (CSV/XLSX) with validation and error handling.
* Manual upload of AAC (Excel) and WAC (CSV) reference files.
* Storage of historical AAC/WAC rates for backdated claims processing.

**3. Data Processing**

* Categorize claims as commercial or federal based on plan identifiers.
* Match NDC + dispense date to AAC; if no match, fall back to WAC.
* Calculate “expected”, “paid”, “owed”, and “method” used (AAC or WAC).
* Allow recalculation if updated AAC/WAC files are uploaded.

**4. Reporting & PDF Generation**

* Generate PBM-specific PDF and CSV reports for underpaid **commercial** claims.
* Store reports securely and list previous reports by date range and PBM.
* Allow users to download reports for email submission.

**5. Email Handling (MVP)**

* System generates “email-ready” content (subject, body, attachment) for PBMs.
* Users send emails from their own HIPAA-compliant desktop email application.
* No in-app email sending for MVP.

**6. Dashboard (Summary View)**

* Totals for number of claims, underpaid claims, and total underpaid amount.
* Basic filters (date range, PBM).

**7. Hosting & Infrastructure**

* Hosted on Liquid Web HIPAA-compliant VPS with 24×7 support.
* Supabase HIPAA-compliant account for database, storage, and authentication.
* Daily backups of app server and database.

**8. HIPAA Compliance (MVP Level)**

* Role-based access control with Row Level Security (single role for MVP).
* All data encrypted at rest and in transit.
* Private storage buckets for all uploaded files and reports.
* Data minimization — exclude PHI from reports unless required and approved.

---

### What We Will NOT Deliver

- Mobile applications (iOS/Android)
- On-premises software installations
- Custom hardware solutions
- EHR system integrations beyond claims data
- Training services beyond documentation
- Ongoing maintenance beyond 30-day warranty period

## Technical Specifications

### Technology Stack

- **Frontend:** Next.js 15 with TypeScript (w/ SSR, ISR, SSG for caching and superfast performance)
- **Backend:** Supabase (HIPPA Complaint)
- **Database:** PostgreSQL with Redis caching
- **Infrastructure:** HIPAA-compliant cloud infrastructure (AWS S3 Storage)
- **Email:** SMTP/SendGrid/Mailgun

### Performance Requirements

- Page load times: < 3 seconds
- File processing: < 30 seconds for 10,000 claims
- Report generation: < 10 seconds
- System uptime: 99.5% availability
- Concurrent users: Support for 200+ simultaneous users

### Security & Compliance

- HIPAA-compliant PHI handling
- Role-based access controls
- Audit logging for all user actions
- Data encryption at rest and in transit
- TLS 1.2+ encryption
- Encrypted database fields

## Project Timeline

| Week | Phase | Deliverable | Acceptance Criteria |
|------|-------|-------------|-------------------|
| 1 | SOW Approval & Kickoff | Project Setup & Requirements | Development environment configured, requirements documented, database schema designed |
| 2-3 | MVP Development Start | Core Platform Development | User authentication, data upload, basic processing functional |
| 4 | Internal Alpha | Analysis & Reporting Engine | Claims categorization, underpayment calculation, PDF generation working |
| 5 | Private Beta | Integration & Automation | Email automation, API framework, dashboard analytics complete |
| 6 | Testing Phase | Testing & Deployment Prep | UAT completed, security testing, performance validation |
| 7 | MVP Launch | Production Deployment | Production deployment, go-live ready, source code delivered |

### Key Milestones

- **August 12, 2025:** SOW Approval & Kickoff
- **August 16, 2025:** MVP Feature Lock
- **August 18, 2025:** Development Start
- **September 10, 2025:** Internal Alpha (Developer Review)
- **September 20, 2025:** Private Beta for Frank's Clinic
- **October 1, 2025:** MVP Launch (Live)

## Deliverables and Acceptance Criteria

### 1. Functional Web Application

**Acceptance Criteria:**

- Users can register, login, and manage pharmacy profiles
- CSV/Excel files upload and process correctly
- Claims are accurately categorized as commercial/federal
- Underpayment calculations match existing prototype results
- PDF reports generate with correct data and formatting
- Emails send automatically to correct PBM addresses
- Weekly Alabama Medicaid rate ingestion working
- Historical rate table maintenance functional
- Backdated claims insertion and re-run capability

### 2. Technical Documentation

**Deliverables (within 30 days of MVP launch):**

- API documentation
- Database schema documentation
- Deployment guide
- User manual
- Administrator guide
- HIPAA compliance documentation

**Note:** Technical documentation will be delivered within 30 days of MVP launch to ensure accuracy and incorporate any bug fixes, system changes, or user feedback identified during the initial deployment period.

### 3. Source Code and Assets

**Deliverables:**

- Complete source code repository
- Database migration scripts
- Deployment configuration files
- Test data and scripts

## Future Development (Post-MVP)

To be scoped and priced under monthly retainer:

- KPI Dashboard / Pharmacy Business Health Metrics
- Multi-State Medicaid rules support
- Pharmacy "Books" system expansion
- Revenue Recapture Service Module (appeal follow-up)
- Enhanced API integrations
- Mobile Optimization (if needed)

## Pricing

### Development Investment: $35,000

**Payment Schedule:**

- 50% ($17,500) - Upon SOW signing and project start
- 30% ($10,500) - Upon completion of core platform (Week 4)
- 20% ($7,000) - Upon successful deployment and acceptance

### Included Services

- 7 weeks of development
- Full buildout of MVP scope
- HIPAA-level security implementation
- Project management, QA, and deployment
- 30 days post-launch bug fixes and support
- Complete technical documentation (delivered within 30 days of launch)
- Production deployment assistance

### Additional Services (Optional)

**Extended Support: $2,500/month**
- **Purpose:** Ongoing maintenance, bug fixes, and basic support
- **Scope:** Keeping the existing system running smoothly
- **Includes:** Server maintenance, security updates, minor bug fixes, user support, system monitoring, backup management, and technical troubleshooting

**Monthly Development Retainer: $3,000 – $6,000/month**
- **Purpose:** Active development of new features and enhancements
- **Scope:** Building new functionality listed in the "Future Development" section
- **Includes:** Developing new features such as:
  - KPI Dashboard / Pharmacy Business Health Metrics
  - Multi-State Medicaid rules support
  - Pharmacy "Books" system expansion
  - Revenue Recapture Service Module (appeal follow-up)
  - Enhanced API integrations
  - Mobile optimization

**Other Services:**
- **Feature enhancements:** $150/hour (for ad-hoc requests outside of retainer)
- **Additional integrations:** Quote upon request
- **Training sessions:** $1,500/day (conducted via online video meeting such as Zoom)

**Note:** Extended Support and Monthly Development Retainer can be purchased separately or together based on client needs.

## Assumptions and Dependencies

### Client Responsibilities

- Frank will provide:
  - Desktop audit tool (zip file)
  - Static Medicaid rate file link
  - PBM contact list
  - Copy for landing pages & domain access (PharmacyBooks.com)
- Provide access to existing Python prototype within 48 hours
- Supply current Medicaid rate data and PBM contact lists
- Provide test data for development and validation
- Participate in weekly progress reviews
- Complete user acceptance testing within 3 business days
- Provide feedback on deliverables within 2 business days

### Technical Assumptions

- Existing prototype algorithms are accurate and complete
- Required reference data (AAC, WAC, PBM contacts) is available
- Pharmacy management system APIs follow standard protocols
- No major regulatory changes during development period
- Frank owns rights to all data and IP created

### Dependencies

- Availability of engineering team (Mical Johnson and team)
- Client approval of technical architecture decisions
- Timely client feedback on development progress
- Access to production hosting environment
- Third-party vendors (email, hosting, compliance) may have separate fees

## Change Management

### Scope Changes

- All scope changes require written approval
- Changes may impact timeline and budget
- Emergency regulatory changes will be accommodated at standard hourly rates

### Timeline Changes

- Client-requested delays may incur additional costs
- Software engineer delays will not impact final pricing
- Force majeure events will be handled case-by-case

## Warranty and Support

### 30-Day Warranty

- Bug fixes at no additional cost
- Performance optimization if requirements not met
- Documentation updates and corrections

### Post-Warranty Support

- Bug fixes: $150/hour
- Feature requests: Quote upon request
- Emergency support: $200/hour (4-hour response)

## Terms and Conditions

### Payment Terms

- Net 15 days from invoice date
- Late fees: 1.5% per month on overdue amounts
- All payments in USD

---

### Architecture

![Cyber Pharma Architecture](https://res.cloudinary.com/dyb0qa58h/image/upload/v1754886691/CYBER-PHARMA-ARCHITECTURE_qbwefl.png)



# 1. Introduction

## 1.1. Project Overview
This document outlines the business requirements for the Retouch Ayutthaya Affiliate Program. This program will allow third-party affiliates (Referrers) to earn commissions by promoting the Retouch Ayutthaya mobile application to new users (Referees). When a Referee makes an in-app purchase through a Referrer's link, the Referrer will receive a percentage of the sale, and the Referee will receive a discount.

## 1.2. Scope
The scope of this project includes:
- A public-facing web dashboard for Referrers to register, manage their account, and track their performance.
- Integration with the mobile application to track referrals and apply discounts for Referees.
- An administrative backend for managing Referrers, payments, and system settings.

## 1.3. Objectives
- To increase user acquisition for the Retouch Ayutthaya application.
- To create a new marketing channel through affiliate marketing.
- To increase in-app purchases.

# 2. Stakeholders

| Stakeholder | Role |
| :--- | :--- |
| Referrer | An individual or entity that promotes the application. |
| Referee | A new user who is referred to the application. |
| Admin | System administrator responsible for managing the program. |
| Development Team | Responsible for building and maintaining the system. |

# 3. Functional Requirements

## 3.1. Referrer Management
- **FR-001:** Any individual should be able to register as a Referrer through a web dashboard.
- **FR-002:** Referrers shall be provided with a unique referral link and QR code.
- **FR-003:** Referrers must provide personal and payment information to be eligible for payouts. This includes Account Type (Individual/Organization), Name, ID Number, Address, and Bank Account details.
- **FR-004:** An Admin must manually verify and approve Referrer accounts.

## 3.2. Referee Management
- **FR-005:** Referees who use a referral link or QR code shall be identified and associated with the corresponding Referrer.
- **FR-006:** Referees shall receive a discount on their first in-app purchase. The discount will be displayed on the paywall with the original price crossed out.
- **FR-007:** The iOS application shall display a "Paste" button on the welcome screen to allow users to apply a referral link from their clipboard.

## 3.3. Commission and Payment
- **FR-008:** Referrers shall earn a commission on in-app purchases made by their Referees.
- **FR-009:** Commissions shall be paid out monthly.
- **FR-010:** A minimum payout threshold must be met for a Referrer to receive a payment.
- **FR-011:** All payments to Referrers shall be processed manually by an Admin.

## 3.4. Referrer Dashboard
- **FR-012:** The dashboard shall be accessible via a web browser at `refer.retouchayutthaya.com`.
- **FR-013:** The dashboard shall be designed with a mobile-first approach.
- **FR-014:** Referrers shall be able to log in using an email and password or a social media account.
- **FR-015:** The dashboard shall display the Referrer's unique referral link and QR code. If the link and QR code are not yet available, a message shall be displayed to inform the user that they are being generated.
- **FR-016:** The dashboard shall display performance metrics including Revenue, Clicks, Commissions, and Sales, along with a performance graph.
- **FR-017:** The dashboard shall provide detailed statistics on sales and commissions.
- **FR-018:** Referrers shall be able to view their payment history (paid and unpaid).
- **FR-019:** Referrers shall be able to manage their personal and account information.
- **FR-020:** The dashboard shall display the status of the Referrer's personal information verification (e.g., "Info is Incorrect", "Under Verification", "Not Verified").

# 4. Non-Functional Requirements

## 4.1. Security
- **NFR-001:** User authentication shall be handled securely using Firebase Authentication.
- **NFR-002:** All sensitive data shall be stored securely in the database.
- **NFR-003:** The system shall use HTTPS for all communication.

## 4.2. Usability
- **NFR-004:** The Referrer Dashboard shall be user-friendly and intuitive.
- **NFR-005:** The dashboard shall support both English and Thai languages.

## 4.3. Performance
- **NFR-006:** The system shall handle a reasonable number of concurrent users without significant degradation in performance.

# 5. System Interfaces

## 5.1. Branch.io
- The system will use the Branch.io SDK for deferred deep linking to track referrals.

## 5.2. RevenueCat
- The system will use RevenueCat to manage in-app purchases and track subscription events.
- RevenueCat will be integrated with Branch.io to attribute purchases to Referrers.
- The system will use RevenueCat's scheduled data exports to get purchase data.

## 5.3. Firebase Authentication
- The system will use Firebase for user authentication on the Referrer Dashboard.

## 5.4. Mailgun
- The system will use Mailgun for sending transactional emails, such as email verification and password reset emails.

## 5.5. OpenExchangeRates.org
- The system will use OpenExchangeRates.org to fetch daily exchange rates for currency conversion.

# 6. Data Requirements

The following data needs to be stored in a MongoDB database:
- Referrer information (ID, name, email, etc.)
- Referee information (ID, Referrer ID)
- Purchase and commission data
- Exchange rates
- Payment records

# 7. Assumptions and Constraints

- **CON-001:** All Admin-related tasks, such as Referrer verification and payments, will be performed manually. The system will not provide an Admin interface for these tasks initially.
- **CON-002:** The system will rely on daily data exports from RevenueCat, which means that the data in the dashboard will not be real-time and will be updated once a day.
- **CON-003:** The initial version of the system will not have automated fraud detection.
- **CON-004:** The system will fetch exchange rates from OpenExchangeRates.org once a day, so the conversion rates may not be the exact real-time rates at the moment of purchase.
- **CON-005:** The generation of the referral link and QR code may take up to 24 hours. The system should inform the user about this delay.

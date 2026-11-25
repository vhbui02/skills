---
name: 23-nfrs
description: Review against 23 Non-Functional Requirements (NFRs)
disable-model-invocation: true
---

Review against 23 Non-Functional Requirements (NFRs), score each from the scale of 0 to 10:

## 1. Security
**Description:** Requirements regarding security throughout system usage, from accessing, performing operations, and printing documents to logging out of the system.

**Examples:**
- User passwords must be hashed using MD5.
- The system deactivates for 30 minutes if a user enters the wrong password 5 consecutive times.
- All sensitive user data (password, phone number, ID number, email) must be encrypted using 1024-bit SSL.
- Password reset links must be sent solely to the initially registered email address.
- The system is not allowed to store users' credit or debit card information during online payments.

---

## 2. Performance
**Description:** The operational efficiency of the system, usually measured by response time per transaction, number of transactions per second, capacity (number of transactions stored or executed per object), and resource usage factors such as RAM and database size.

**Examples:**
- All data input and output screens must be ready to display within 3 seconds under normal load (30 concurrent users without load balancing), minimum server specs (Intel Core i5, 4GB RAM, 500GB hard disk), and a 500KB/s client/server connection:
  - **Input screens:** Maximum of 30 fields, no complex calculations, no external system interaction, direct database saving, and no large files over 3MB.
  - **Output screens:** Direct database queries, displaying up to 50 rows by 10 columns with each value under 100 characters.

---

## 3. Usability
**Description:** The ease of use of the system, evaluated through five factors:
- **Effectiveness:** Doing exactly what is expected.
- **Efficiency:** Completing tasks faster and more accurately.
- **Engagement:** UI matching end-users and usage context.
- **Error Tolerance:** Being forgiving of user input mistakes.
- **Easy to learn:** Consistency across forms and screens.

**Examples:**
- **Effectiveness:** Displaying inventory quantity directly next to the warehouse name so users do not need an extra click.
- **Efficiency:** Reducing milk tea ordering from 5 taps to 3 taps with clear button labels.
- **Engagement:** Not designing a manufacturing planning system to look cute like a baby store website.
- **Error Tolerance:** Validating each field immediately instead of wiping all 20 entered customer fields upon saving.
- **Easy to learn:** Keeping the Navigation bar, Command bar, and New button in consistent positions across Customer and Order forms.

---

## 4. Integrity
**Description:** The accuracy and validity of data, requiring that data be calculated accurately at all times even when undergoing complex multi-source processing via synchronous and asynchronous background batch jobs.

**Examples:**
- Calculating a final order total by combining order info, external promotion data (price, discounts, freebies), and 4?5 additional parameters without asynchronous batch jobs overlapping with synchronous ones and yielding wrong results when a user refreshes the screen immediately instead of waiting 30 seconds.

---

## 5. Availability
**Description:** Requirements regarding the readiness of the system to be used, consisting of the time the system is available for use and operational dependencies.

**Examples:**
- The system must operate 24/7, upgrade at most once every 3 months, and have no more than 1 hour of downtime per year.
- The system must operate 24/7 without depending on the downtime of any third-party add-ons or products.

---

## 6. Audit
**Description:** Requirements regarding the ability to record actions performed on the system strictly for inspection and auditing purposes, rather than for statistics or reporting.

**Examples:**
- Audit data must be stored in a separate database from the main system database.
- System data must be backed up daily and retained for 30 days.
- Audit data must be Read-Only and cannot be modified from the user interface.

---

## 7. External Interface
**Description:** Requirements regarding system integration, specifying how components of the system being built exchange data with components of other systems, including exchanged components, purpose, frequency of change, and number of impacted users.

**Examples:**
- All data must be integrated via APIs.
- APIs must return results in JSON or XML format.
- The entire process of sending and receiving data between systems must be detailed in documentation.

---

## 8. User Interface
**Description:** Specific requirements for the user interface desired by the customer, covering UI structure, warnings, error messages, and other interface standards (narrower in scope than Usability).

**Examples:**
- All data grids must have filter and sort functions.
- Delete actions must prompt for Y/N confirmation.
- All error messages must provide troubleshooting guidance.
- Encourage vertical scrolling and minimize horizontal scrolling.
- Default screen resolution of 1024×768 pixels.
- Sequential multi-step processes must have a detailed progress bar.
- All dropdown lists must be sorted A to Z and in ascending numerical order.

---

## 9. Migration
**Description:** Requirements governing the transfer and synchronization of data from an old system or environment to a new system or environment.

**Examples:**
- Migrating all 250,000 customer records, 12,500 product records, and 500 price list records from the old ABC system to the new ABC system.

---

## 10. Supportability
**Description:** Requirements describing the environments, devices, or platforms on which the system must run well.

**Examples:**
- Devices and platforms supported by the Microsoft Dynamics 365 solution.

---

## 11. Compliance
**Description:** Requirements ensuring the system complies with legal regulations, government laws, company policies, financial laws, land laws, environmental laws, child and wildlife protection laws, and general industry rules.

**Examples:**
- Compliance with regulations of international payment organizations, maritime regulations, and sea transport regulations.

---

## 12. Flexibility
**Description:** Requirements regarding the system's ability to adapt to different environments, such as different organizations, geographical regions, or industries.

**Examples:**
- Microsoft Dynamics 365 operating effectively across manufacturing, media, banking, and healthcare in over 120 countries.
- A solution deployed across Vietnam, Laos, Cambodia, Mongolia, and Saudi Arabia needing to support both Latin alphabets and non-Latin scripts.

---

## 13. Scalability
**Description:** The ability of the system to expand its operational capacity to handle increased load or transaction volume in the future.

**Examples:**
- Designing an e-commerce backend currently handling 500 concurrent orders to scale up after 2 years.
- Servers capable of hardware upgrades.
- Separating the database and backend onto different servers.
- Applying a load balancer using HA Proxy.
- Splitting a master database into sub-databases and synchronizing back.

---

## 14. Extensibility
**Description:** The ability to expand the functional scope of a solution by developing new features without negatively impacting existing features.

**Examples:**
- Ability to develop an additional Marketing cost management module for retail channels without altering the existing data structure.
- Ability to develop an inventory checking feature without changing the existing data structure.

---

## 15. Localization
**Description:** Requirements regarding the local characteristics of a solution, including local language and spelling/pronunciation, local laws, local currency, culture, and specific traits of end-users.

**Examples:**
- Choosing between British English and American English (such as *"behaviour"* vs. *"behavior"*).
- Implementing an accounting module for a business in Vietnam versus one in Venezuela, where accounting books, laws, and documents are completely different.

---

## 16. Purchased Component
**Description:** Requirements describing components in the system that the customer must pay to use, detailing their features, limitations, compatibility, and upgrade procedures.

**Examples:**
- Purchasing an existing Loyalty management solution on a monthly subscription to use with Dynamics 365 Customer Engagement (CRM) instead of building one from scratch, detailing its features, limitations, compatibility with Dynamics 365 versions, and upgrade processes.

---

## 17. Maintainability
**Description:** Requirements regarding how easily the system can be maintained, specifically how easily bugs can be detected, diagnosed, and fixed through clean architecture, clear coding conventions, and thorough documentation.

**Examples:**
- Each periodic quarterly system upgrade must not last more than 30 minutes.
- All JavaScript and .NET code must follow ABC XYZ coding conventions.
- Documentation and code must go through a 2-level internal review.

---

## 18. Safety
**Description:** Requirements specifying that the system must not cause harm to the environment or human health during its intended use.

**Examples:**
- In a medical examination management system for hospital ABC, prescriptions must be manually approved by a doctor clicking the **Approve** button before being printed and given to patients to prevent harmful errors.

---

## 19. Legal and Copyright
**Description:** Requirements specifying necessary legal procedures, intellectual property ownership, and proper rules for using a customer's wordmark, trademark, and logo.

**Examples:**
- All Intellectual Property Rights (IPR) related to products or accompanying documents created by ABC belong to the customer.
- Displaying the customer's logo accurately according to frame, color palette, size, and background color without cropping or distorting colors.

---

## 20. Installability
**Description:** Requirements regarding system installation?including new installation, reinstallation, upgrading, and uninstallation?such as maximum steps, who performs it, and their required technical skills.

**Examples:**
- System installation for users must be carried out by the software development partner or a customer System Administrator with at least 3 years of experience in C# and related libraries.
- Upgrading a plugin must not alter system data or data structures.

---

## 21. Accessibility
**Description:** Requirements regarding the system's ability to support users in operating it, especially users with disabilities.

**Examples:**
- An e-Learning system supporting TEXT versions alongside AUDIO versions for hearing-impaired users.
- Supporting voice control for visually impaired users.

---

## 22. Reusability
**Description:** Requirements regarding the ability to reuse one or more parts of the system.

**Examples:**
- Reusing the source code of a Frequently Asked Questions (FAQ) section from an e-commerce site to build other e-commerce sites for subsidiary companies.

---

## 23. Online Manual
**Description:** Requirements specifying online user support functions built directly into the system for immediate reference.

**Examples:**
- A **HELP** button in the top-right corner of the screen that opens an online documentation page (as in Dynamics 365).
- Displaying a popup message providing immediate troubleshooting instructions when a user performs an erroneous action.

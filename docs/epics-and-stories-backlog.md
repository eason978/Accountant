# Epics and User Stories Backlog

This document contains the complete backlog of Epics and User Stories for the Accountant project, broken down from the architecture and front-end specification documents.

---

### **Epic 1: User Onboarding & System Setup**
This Epic covers everything a user needs to do to get started, from creating an account to successfully connecting their Firefly III instance.

*   **User Story 1.1:** As a new user, I want to be able to register for an account, so that I can start using the service.
*   **User Story 1.2:** As a registered user, I want to be able to log in to my account, so that I can use the import functionality.
*   **User Story 1.3:** As a logged-in user, I want to navigate to a "Settings" page, so that I can manage my Firefly III API connection.
*   **User Story 1.4:** On the settings page, I want to be able to enter my Firefly III URL and Personal Access Token and have the system test the connection's validity, so that I can be sure I've provided the correct credentials.
*   **User Story 1.5:** As a user, I want my Firefly III credentials to be stored encrypted, so that my financial data is secure.

### **Epic 2: Core Document Import & Parsing Workflow**
This Epic focuses on the core functionality of the application: uploading a document and having it automatically parsed by the backend.

*   **User Story 2.1:** As a user, I want to see a clear file upload area on the dashboard, so I can easily start a new import job.
*   **User Story 2.2:** I want to be able to upload a financial document (e.g., PDF, JPG, PNG) by either drag-and-drop or clicking to select a file.
*   **User Story 2.3:** After I upload a file, the system should start processing it in the background by creating a new "Import Job", without blocking my UI.
*   **User Story 2.4:** During file processing, I want to see a clear "Processing" status on the UI, so I know the system is working.

### **Epic 3: Transaction Review & Mapping Interface**
This Epic covers the core workbench where users interact with the results of the AI parsing.

*   **User Story 3.1:** Once a document is parsed, I want to see all the extracted transaction data in a clear table.
*   **User Story 3.2:** I want to be able to edit the date, description, and amount for each transaction directly in the table, so I can correct any potential parsing errors.
*   **User Story 3.3:** For each transaction, I want to see dropdown menus to map it to my Firefly III source account, destination account, and category.
*   **User Story 3.4:** These mapping dropdowns need to be dynamically populated with the actual account and category data from my Firefly III instance.
*   **User Story 3.5:** I want to be able to batch-select multiple transactions and apply the same category or account to all of them at once, to improve my efficiency.

### **Epic 4: Automated Mapping Rules Management**
This Epic focuses on implementing the "training mode" to allow the system to remember user preferences.

*   **User Story 4.1:** In the settings page, I want a management section for "My Rules".
*   **User Story 4.2:** I want to be able to create a new mapping rule by specifying a keyword from a transaction's description (e.g., "UBER") and a target category (e.g., "Transportation").
*   **User Story 4.3:** When a new document is parsed, the system should automatically apply my saved rules to pre-fill mappings, reducing my manual effort.
*   **User Story 4.4:** I want to be able to view and delete the mapping rules I have previously created.

### **Epic 5: Final Import to Firefly III**
This Epic covers the final step of pushing the curated data to its destination.

*   **User Story 5.1:** When I'm done reviewing and mapping all transactions, I want to click an "Import" button to send them all to my Firefly III instance at once.
*   **User Story 5.2:** After a successful import, I want to see a success confirmation message, and the import job's status on the dashboard should update to "Completed".
*   **User Story 5.3:** If an error occurs during the import (e.g., connection to Firefly III is lost), I want to see a clear error message so I can resolve the issue.

### **Epic 6: (Technical) Foundational Infrastructure & Deployment**
This is a technical Epic for establishing the project's foundation.

*   **Tech Task 6.1:** Set up the Monorepo project structure with `apps/web`, `apps/api`, and `packages/shared-types` as defined in the architecture document.
*   **Tech Task 6.2:** Initialize the Next.js frontend application and integrate Material-UI (MUI).
*   **Tech Task 6.3:** Initialize the FastAPI backend application.
*   **Tech Task 6.4:** Create the initial database schema in Supabase based on the data models.
*   **Tech Task 6.5:** Set up a basic CI/CD pipeline to automatically run tests and builds on code commits.

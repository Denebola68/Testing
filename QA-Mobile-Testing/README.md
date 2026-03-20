# Portfolio Project: QA Mobile Testing – Maternity Companion App

## 📋 Project Overview
This project focuses on the comprehensive Quality Assurance testing of a **gamified maternity tracking application**. The app is designed to support expectant parents through task management, health monitoring (contraction timers, fetal movement tracking), and financial logistics, all wrapped in a military-themed progression system including ranks and XP.

---

## 🎯 Testing Objectives
The primary goal was to ensure the reliability of core health-related features, data integrity during offline usage, and the accuracy of pregnancy-related calculations.

### **Testing Scope**
* **Functional Testing:** Validated core features such as the contraction timer, fetal movement monitor, and task completion logic.
* **Boundary Value Analysis:** Tested pregnancy date inputs to ensure the logic handles past dates and extreme future dates correctly.
* **Interruption & Connectivity Testing:** Evaluated app behavior during forced closures and transitions to Airplane mode to verify "Offline-First" support.
* **UI/UX Evaluation:** Identified inconsistencies in the interface, including text formatting issues (censure-like characters) and non-responsive elements in landscape mode.

---

## 🛠️ Environment & Tools
* **Device:** Android Physical Device.
* **Tools:** Google Sheets (Documentation), Screen Recording.

---

## 🐞 Key Findings & Bug Report
A total of **25 defects** were identified, ranging from UI/UX improvements to critical logic failures.

### **Critical Defects Summary:**
1.  **Data Loss in Offline Mode:** Newly created tasks and inventory updates failed to persist after the app was closed in Airplane mode.
2.  **Pregnancy Logic Errors:** Incorrect calculation of gestation months based on the user-provided due date (e.g., displaying the 8th month instead of the 7th).
3.  **Timer Reset Issues:** The contraction timer resets if the user navigates to a different tab within the application.
4.  **Authentication Delays:** Google OAuth registration experienced delays exceeding 60 seconds.

---

## 📈 Strategic Recommendations (UX Improvements)
Beyond defect reporting, I provided strategic feedback to improve user experience:
* **Input Flexibility:** Implementation of manual keyboard entry for dates instead of restricted scroll-wheel selectors.
* **Health Logic Refinement:** Preventing the system from declaring "regular contractions" based on a single data point.
* **Personalization:** Better integration of the user-selected "Commander Name" throughout the UI to enhance gamification.

---

### **Deliverables**
The full anonymized bug report table is available in the repository documentation. UI elements and branding have been intentionally blurred/redacted to protect the intellectual property of the original developer.
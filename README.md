# MyCharacterList-QA-Portfolio
# 🎯 QA Testing Portfolio - MyCharacterList Web Application

Welcome to my QA Testing Portfolio! This repository contains the testing documentation, execution records, and defect management reports for **MyCharacterList** – a full-stack web application that allows users to create, rank, and share tier lists of their favorite characters, featuring a dynamic Global Leaderboard and a social community system.

The goal of this project was to perform comprehensive **Manual Testing** (Functional, UI/UX, Backend API, and Security) to ensure system stability, data integrity, and a seamless user experience prior to the production release.

---

## 🔗 Quick Links

* 🌐 **Live App:** [Click here to view the live website](https://mycharacterlist.netlify.app/)
* 📊 **Test Execution Sheet:** [Click here to view the Google Sheets](https://docs.google.com/spreadsheets/d/1h6TIYJiNofGMxebUR5WtZh4RzmJaeCgCJqgm1MCR-Ww/edit?usp=sharing)
* 🗂️ **Test Plan (STP/STD):** [Link to your STP document]

---

## 📈 Test Execution Summary

A rigorous and exhaustive test suite was designed and executed, covering Authentication, List Management, Community Interactions, and API endpoints.

| Metric | Count |
| :--- | :--- |
| **Total Tests Executed** | 158 |
| **Tests Passed ✅** | 152 |
| **Bugs Found (Failed) 🐞** | 6 |
| **UX Enhancements Suggested 💡** | 2 |


> *Note: All failed tests were logged as defects in Jira, tracked through their lifecycle, and re-tested upon deployment of developer fixes.*

---

## 🐞 Jira Defect Management

All bugs discovered or improvements suggested during execution were logged, prioritized, and managed using a **Jira Kanban Board** to simulate a real Agile/Scrum QA workflow.

### 📋 Jira Kanban Board Overview
![Jira Kanban Board Placeholder](https://ibb.co/G4nw5qPB)
*(Replace this image with a screenshot of your actual Jira board)*

---

### 🔍 Highlighted Bug Reports

Here are 3 critical/medium bugs found during the testing cycle, demonstrating my ability to write clear, reproducible, and developer-friendly defect reports across different system layers (UI, Logic, and Backend API).

#### Bug 1: [Auth/UI] Guest Community Modal displays "No users found"
* **Ticket ID:** KAN-6
* **Priority:** 🟠 Medium
* **Description:** When a logged-out guest user attempts to explore the community by clicking the "See more of our community..." button on the landing page, the modal opens successfully but fails to load the user grid, displaying a false "No users found" state instead.
* **Steps to Reproduce:**
  1. Navigate to the Home page as a logged-out Guest.
  2. Scroll down to the "Explore Community Lists" section.
  3. Click the outline button: "See more of our community...".
* **Expected Result:** The Community Modal opens and the grid populates with community users (with guest restrictions applied, e.g., no follow button).
* **Actual Result:** No users are displayed and the grid says "No users found."
* **Jira Screenshot:**
  <br>![Bug 1 Screenshot](https://via.placeholder.com/600x300?text=Insert+Jira+Ticket+Screenshot+Here)

#### Bug 2: [Profile/Logic] Empty public lists are visible on user profiles
* **Ticket ID:** KAN-9
* **Priority:** 🟡 Low
* **Description:** Public lists that contain 0 characters are supposed to be hidden from the public profile view to prevent visual clutter and empty states. However, the system currently fails to filter them out, rendering empty list cards to profile visitors.
* **Steps to Reproduce:**
  1. Log in and ensure User A has a "Public" list with 0 characters added to it.
  2. Open User A's profile page.
  3. Check the "Public Lists" grid section.
* **Expected Result:** The empty list does NOT appear in the "Public Lists" section.
* **Actual Result:** The list appears with 0 items.
* **Jira Screenshot:**
  <br>![Bug 2 Screenshot](https://via.placeholder.com/600x300?text=Insert+Jira+Ticket+Screenshot+Here)

#### Bug 3: [Backend/API] Jikan Search Endpoint returns empty JSON
* **Ticket ID:** KAN-8
* **Priority:** 🔴 High
* **Description:** When querying the internal backend API for Anime characters (which acts as a proxy to the Jikan API), the server responds with a 200 OK status, but the JSON payload is completely empty. This breaks the character search functionality on the frontend.
* **Steps to Reproduce:**
  1. Open Postman.
  2. Send a `GET` request to `{{baseURL}}/api/search/jikan?query=Goku`.
* **Expected Result:** HTTP Status 200 OK. The response is a properly formatted JSON array containing objects with id, title, image, and type: "character".
* **Actual Result:** HTTP Status is "200 OK" but the JSON is empty `[]`.
* **Jira Screenshot:**
  <br>![Bug 3 Screenshot](https://via.placeholder.com/600x300?text=Insert+Jira+Ticket+Screenshot+Here)

---

## 🛠️ Tools & Technologies Used

During this project, I utilized the following tools and testing methodologies to ensure high-quality software delivery:

### ⚙️ Tools
* **Browser DevTools (Chrome/Firefox):** Deep inspection of DOM elements, monitoring Network API payloads (Responses/Headers), and managing Application Storage (Cookies/JWT validation).
* **Postman:** Directly testing Backend API endpoints (GET/POST/PUT/DELETE) and validating JSON responses independently of the frontend UI.
* **Jira:** Defect tracking, Agile Kanban board management, setting Priorities and Severities, and attaching reproduction steps.
* **Google Sheets:** Designing, structuring, and executing the 158-case Test Matrix (STD).

### 🧪 Testing Methodologies
* **End-to-End (E2E) Testing:** Validating full user flows (e.g., Registering -> Creating a list -> Adding a character -> Sharing the list).
* **API Testing:** Bypassing the UI to test backend logic, status codes, and JSON data structuring.
* **Negative Testing:** Intentionally inputting invalid data to verify error handling and application resilience.
* **Cross-Browser & Responsiveness:** Verifying mobile grid logic, hamburger menus, and layout scaling.

---
*Thank you for reviewing my QA Portfolio! Feel free to reach out if you have any questions.*

Phase 6: Project Testing
Overview

This document outlines the test cases, execution steps, and verification results for the UI Policies and Client Scripts configured on the Incident table.
Unit Test Cases
Test Case 1: Mandatory Assigned To Field Validation

    Feature: Mandatory "Assigned To" Field
    Pre-condition: Open a new or existing incident form (incident.do).
    Test Steps:
       1. Set Impact to 1 - High.
       2. Leave the Assigned to field empty.
       3. Attempt to save or submit the form.
    Expected Result: The system blocks form submission and displays the red error message: "Assigned To is mandatory for High impact incidents".
    Status: Passed
    <img width="945" height="441" alt="Screenshot 2026-09-30 151109" src="https://github.com/user-attachments/assets/da7c65bd-7a28-4482-b0fe-687da4b657ac" />
    Test Case 2: Auto-Set Urgency to High Validation

    Feature: Auto-Set Urgency & Read-Only Logic
    Pre-condition: Open an incident form where Impact is set to Medium or Low.
    Test Steps:
        Change Impact to 1 - High.
    Expected Result: Urgency automatically changes to 1 - High and becomes read-only.
    Status: Passed
<img width="946" height="526" alt="image" src="https://github.com/user-attachments/assets/ff6999da-1f81-40a7-9356-6a95f9377d95" />

Test Case 3: Reverse Condition Logic (Impact Change)

    Feature: onChange Client Script for Urgency Field
    Pre-condition: Incident Impact is currently set to 1 - High.
    Test Steps:
        Change Impact from 1 - High to 2 - Medium.
    Expected Result: The Urgency field becomes editable again.
    Status: Passed
    <img width="947" height="527" alt="image" src="https://github.com/user-attachments/assets/5e4b45a4-924b-48f9-8a5d-17d3c198c1ef" />
Test Case 4: Block List Editing on State Field

    Feature: onCellEdit Client Script on State Field
    Pre-condition: Navigate to the Incident list view (incident.list).
    Test Steps:
        Double-click the State cell for any incident in the list view.
        Attempt to edit the value.
    Expected Result: An alert popup appears stating "State cannot be updated using list editing. Please open the Incident." and the change is canceled.
    Status: Passed
<img width="948" height="529" alt="image" src="https://github.com/user-attachments/assets/9b3c8079-287c-4f50-974f-750139f48815" />

TEST CASE4.1: EDITING THROUGH FORM
<img width="948" height="530" alt="image" src="https://github.com/user-attachments/assets/2f9a8dfa-2ea3-48be-a4b0-3218d56e5c39" />

AFTER EDITING ON VIEW INCIDENT
ONHOLD CHANGED TO IN PROGRESS
<img width="947" height="528" alt="image" src="https://github.com/user-attachments/assets/43c1003a-61cd-47f9-90df-b0536d825b25" />







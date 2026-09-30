****Phase 7: Project Documentation
Technical Configuration Summary
Feature / Artifact 	Type 	Target Table 	Target Field 	Key Logic / Action
High Impact Control 	UI Policy 	incident 	Impact 	Triggers when Impact = 1 - High. Sets urgency to Read-only and assignment_group to Mandatory.
Auto set urgency 	Client Script (onChange) 	incident 	Impact 	Sets urgency value to 1 and adds an Info Message banner on High Impact selection.
Prevent save if Assigned To missing 	Client Script (onSubmit) 	incident 	Form Level 	Cancels submission (return false) and shows an error under assigned_to if empty on High Impact.
Prevent state change via list edit 	Client Script (onCellEdit) 	incident 	State 	Cancels inline list edit (callback(false)) and alerts user to open the Incident record.
System Configuration Details
1. Instance Details

    Instance URL: dev425939.service-now.com
    Application Scope: Global
    Target Table: Incident [incident]

2. UI Policy Setup

    Policy Name: High Impact Control
    Conditions: Impact IS 1 - High
    Reverse if false: true
****
<img width="948" height="535" alt="image" src="https://github.com/user-attachments/assets/6c55e988-06e5-4147-b35b-f1f594bff6e7" />
<img width="944" height="530" alt="image" src="https://github.com/user-attachments/assets/06466f2c-c0d4-47d7-bee0-f06f1adbfa54" />

3. Client Scripts Setup
A. onChange Client Script

    Name: Auto set urgency for high impact
    Type: onChange | Field Name: Impact
   <img width="947" height="529" alt="image" src="https://github.com/user-attachments/assets/775f7376-eb57-44c6-b06c-d599a6cc84bb" />

B. onSubmit Client Script

    Name: Prevent save if Assigned To missing
    Type: onSubmit
    
    <img width="944" height="527" alt="image" src="https://github.com/user-attachments/assets/f17c2809-5792-4472-a0b8-c5aea4ac57f3" />

C. onCellEdit Client Script

    Name: Prevent state change via list edit
    Type: onCellEdit | Field Name: State
  
<img width="944" height="527" alt="image" src="https://github.com/user-attachments/assets/d6cdce64-ec2b-4c5c-945c-4c5ae6aed0bf" />




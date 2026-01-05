# Insurance Verification Workflow with Urgency Routing (n8n)

## Overview
This project implements an automated insurance verification workflow using n8n.  
The workflow processes patient insurance requests, evaluates urgency and confidence levels, and dynamically routes each case for either automated processing or manual human review.

The system is designed to prioritize urgent cases, reduce manual workload, and ensure reliable handling of low-confidence or high-risk scenarios.

---

## Workflow Description
The workflow begins with an incoming request through a webhook and follows a structured decision-based routing process:

1. Patient data is received via a webhook trigger.
2. Incoming data is normalized to ensure consistent structure.
3. The case is evaluated to determine whether it is **urgent**.
4. Based on urgency and confidence levels, the workflow:
   - Automatically processes high-confidence cases
   - Routes low-confidence cases for human review
5. Notifications are sent to the appropriate insurance or manual review teams via email.

---

## Key Workflow Steps

### 1. Webhook Trigger
- Accepts incoming patient insurance verification requests.
- Acts as the entry point for the automation.

### 2. Normalize Patient Data
- Cleans and standardizes patient information.
- Ensures downstream nodes receive consistent data.

### 3. Urgency Evaluation
- Determines whether the case should be treated as **URGENT** or **NORMAL**.
- Applies tagging for traceability and routing.

### 4. Confidence-Based Routing
- Urgent cases:
  - High confidence → Fast-track automated processing
  - Low confidence → Immediate human review
- Normal cases:
  - High confidence → Standard automated processing
  - Low confidence → Queued for manual review

### 5. Notifications
- Sends patient credentials and case details to:
  - Insurance company (automated paths)
  - Manual review teams (human intervention paths)

---

## Features
- Rule-based urgency classification
- Confidence-driven decision routing
- Automated vs manual processing separation
- Email-based notification delivery
- Scalable and modular workflow design

---

## Use Cases
- Insurance claim verification
- Healthcare workflow automation
- Priority-based case handling
- Reducing manual intervention in repetitive processes

---

## How to Use
1. Import the workflow JSON file into n8n.
2. Configure required credentials (Webhook, Email/Gmail, etc.).
3. Activate the workflow.
4. Send test requests to the webhook endpoint.

---

## Notes
- Credentials and sensitive information are not included in this repository.
- Workflow logic can be extended with additional validation or integrations.

---

## Author
Harshitha H 


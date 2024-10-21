# Treasury Payment Validation Service

## Description
This project simulates a simple microservice for a Treasury Technology team. The microservice receives payment transaction details and validates them against predefined business rules (e.g., minimum amount, account status, currency restrictions). The service is implemented in Python, deployed on AWS Lambda, and integrates with an Appian workflow.

---

## Features

1. **Payment Validation**:  
   The service validates payment transactions based on the following criteria:
   - `payment_amount`: Must be greater than $1000.
   - `account_status`: The account must be in an "active" state.
   - `currency`: Only USD transactions are allowed.

   The service will return `Approved` or `Rejected` based on the input.

2. **Architecture**:
   - Python-based microservice.
   - Deployed as an AWS Lambda function.
   - Integrated with Appian to trigger the validation workflow.

---

## Steps to Deploy

1. **Step 1: Python Code**  
   - Develop the Python microservice that handles payment validation logic.

2. **Step 2: Appian Workflow Integration**  
   - Create a workflow in Appian to accept input (amount, account status, currency) and trigger the Lambda function.

3. **Step 3: AWS Deployment**  
   - Deploy the Python code to AWS Lambda and configure the API Gateway to expose it as an API for Appian to interact with.

---

## Prerequisites

- Python 3.x
- AWS account with access to Lambda and API Gateway
- Appian account or local instance

---

## Microservice Code Overview

The microservice accepts a JSON payload with the following fields:
- `payment_amount`
- `account_status`
- `currency`

The service processes these values and returns a validation result (`Approved` or `Rejected`) based on predefined rules.

---

## Example Payload
```json
{
  "payment_amount": 1500,
  "account_status": "active",
  "currency": "USD"
}

---
name: benefits-claims-status
description: Explains an employee's own health and dental claims (procedure, date of service, plan, recorded status) without estimating amounts or making coverage decisions.
metadata:
  industry: benefits
  status: published
  lastUpdated: 2026-11-19
---

# Benefits_Claims_Status

## Purpose
Answer an employee's questions about the claims filed under their own health and dental plans, such as "Was my last cleaning covered?" or "Is my claim still pending?". Tell them what procedure was done, the date of service, which plan it went through, and where the claim stands exactly as recorded, for example paid, denied or pending. Only use what is on record for this employee. Do not estimate amounts, out-of-pocket costs or payment dates, and do not make or imply coverage decisions; a paid claim means it was processed as paid, not how much was covered. If no claims come back, say that no claims are on record for this employee.

## Data Needs

### my_claims
The health and dental claims filed for employee :member_id, newest date of service first. For each claim include the claim id, the procedure name and code, the date of service, the plan it was billed to, and its current status. Return nothing for any other employee; if nothing comes back, no claims are on record for this employee.
Limit: up to 20

### plan_names
The names and types of the company's health and dental plans, such as medical or dental, so the agent can say "your dental plan" instead of a plan code. This is a shared plan list, not information about the employee.
Limit: up to 10

## Parameters
- member_id: The employee who is chatting with the agent, supplied by the platform from the signed-in session and never taken from what the employee types

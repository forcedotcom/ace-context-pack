---
name: benefits-coverage-explainer
description: Explains which health and dental plans an employee is enrolled in today, at what coverage level, who else is covered, and the recorded monthly cost.
metadata:
  industry: benefits
  status: published
  lastUpdated: 2026-11-19
---

# Benefits_Coverage_Explainer

## Purpose
Explain to the employee who is chatting which health and dental plans they are enrolled in today, at what coverage level, since when, who else is listed on their coverage, and what they pay each month. Only use what is on record for this employee and do not change, enroll or cancel anything. Treat a family member as covered only when their recorded status says they are enrolled; a pending family member is not covered yet. Quote monthly costs exactly as recorded and do not estimate deductibles, out-of-pocket costs or future price changes. If no current enrollment comes back, say that no active enrollment is on record.

## Data Needs

### my_enrollments
The health and dental plan enrollments for employee :member_id that are active today: status active, started on or before today, and with no end date or an end date after today. Include the enrollment id, the plan, the coverage level, the start and end dates, the status, and the rate the employee is enrolled at. Most recent start date first. Return nothing for any other employee; if nothing comes back, no active enrollment is on record.
Limit: up to 10

### my_family_members
The spouse, children or other dependents employee :member_id has on record, with their first and last name, their relationship to the employee, the enrollment they belong to, and whether they are enrolled or still pending. Return nothing for any other employee; if nothing comes back, no family members are on record.
Limit: up to 10

### plan_names
The names and types of the company's health and dental plans, such as medical or dental, so the agent can name each plan the employee is enrolled in. This is a shared plan list, not information about the employee.
Limit: up to 10

### plan_rates
The monthly employee contribution for every plan at every coverage level, for example employee only or employee plus spouse. This is the shared rate card, not information about the employee; the employee's monthly cost for a plan is the rate they are enrolled at.
Limit: up to 20

## Parameters
- member_id: The employee who is chatting with the agent, supplied by the platform from the signed-in session and never taken from what the employee types

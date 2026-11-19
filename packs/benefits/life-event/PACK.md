---
name: benefits-life-event
description: Helps an employee understand how a recent life event such as marriage affects their health and dental benefits, including family members on record and the extra monthly cost from recorded rates.
metadata:
  industry: benefits
  status: published
  lastUpdated: 2026-11-19
---

# Benefits_Life_Event

## Purpose
Help an employee who recently had a life event, such as getting married, understand what it means for their health and dental benefits. Tell them which life event is on file and whether their supporting documents were verified, which family members are on record and whether they are already covered or still waiting to be enrolled, which plans they are on today, and how much more they would pay each month to add their family. Only use what is on record for this employee. Never enroll anyone, never promise that a change is approved or effective, and never invent deadlines or effective dates. Work out any extra monthly cost only from the recorded rates for the same plan, and say which coverage levels you compared. If something the employee asks about is not on record, say so.

## Data Needs

### life_events
The life events employee :member_id has reported, such as a marriage, most recent first. Include the type of event, the date it happened, whether and when the employee reported it, whether their supporting documents have been verified, and the family member and enrollment it relates to. Return nothing for any other employee; if nothing comes back, no life event is on record.
Limit: up to 5

### family_members
The spouse, children or other dependents employee :member_id has told us about, with their first and last name, their relationship to the employee, the enrollment they belong to, and whether they are already covered or still pending enrollment. Include pending family members with their status. Return nothing for any other employee; if nothing comes back, no family members are on record.
Limit: up to 10

### current_coverage
The health and dental plan enrollments for employee :member_id that are active today: status active, started on or before today, and with no end date or an end date after today. Include the enrollment id, the plan, the coverage level, the start and end dates, the status, and the rate the employee is enrolled at. Most recent start date first. Return nothing for any other employee; if nothing comes back, no active enrollment is on record.
Limit: up to 10

### plan_names
The names and types of the company's health and dental plans, such as medical or dental, so the agent can name each plan. This is a shared plan list, not information about the employee.
Limit: up to 10

### plan_costs
The monthly employee contribution for every health and dental plan at every coverage level, for example employee only versus employee plus spouse. This is the shared rate card, not information about the employee; compare the employee's current coverage level with the level that would include their family on the same plan.
Limit: up to 20

## Parameters
- member_id: The employee who is chatting with the agent, supplied by the platform from the signed-in session and never taken from what the employee types

### 1. The Purpose: Measuring the "Burnout Reservoir"
Most attrition models only look at whether someone is working overtime *now*. However, a person can usually handle high stress for 6 months. By the 3rd year, that stress becomes a "toxic reservoir."

* **`total_overtime_hours_in_current_role`**: This represents the **Total Fatigue** accumulated in their current position.
* **`burnout_risk_flag`**: This identifies the "Unsung Martyrs"—people working massive hours who aren't even being financially compensated for the extra time.

---

### 2. Impact on Attrition Hypothesis
This feature allows you to test the **"Exploitation Hypothesis"**:

* **The "Breaking Point" Hypothesis:** There is likely a specific number (e.g., 1,500 total lifetime OT hours) where an employee’s probability of leaving jumps from 10% to 50%.
* **The "Fairness" Hypothesis:** If an employee is `overtime_paid_eligible == 'No'` but has a high `total_overtime_hours`, they feel the company is "stealing" their time. This leads to **resentment-based attrition**, which is much harder to fix with a simple bonus.
* **The "Role Exhaustion" Hypothesis:** It helps you identify if certain roles (like "Junior Analyst") are being used as "churn-and-burn" roles where people stay for 2 years and then quit due to exhaustion.

---

### 3. Brief Explanation for Understanding
Think of it like a **Battery**. 
> "Every week of overtime drains 1% of the battery. If you've been in the role for 3 years with high OT, your battery is at 0%. If the company isn't 'charging' that battery with extra pay (`overtime_paid_eligible`), the employee will simply shut down and leave to find a job that doesn't drain them."

**Expert Consultant Move:** Try grouping by `job_role` and looking at the average `total_overtime_hours_in_current_role`. If one role has 2,000 hours and another has 100, you've found exactly where your "Attrition Leak" is coming from.

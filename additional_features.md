
### 1. The "Stability & Loyalty" Features
These help you test the hypothesis that **restless employees or those who feel "stuck" are more likely to leave.**

* **Average Tenure per Company:** `total_working_years / num_companies_worked`
    * **Why:** If someone has 10 years of experience but has worked at 10 companies, they are a "job hopper."
    * **Impact:** High job-hopping history is a massive predictor of future attrition.
* **Role Stagnation Ratio:** `years_in_current_role / years_at_company`
    * **Why:** If a person has been at the company for 10 years but in the same role for 9, they are likely bored or overlooked.
    * **Impact:** Tests the hypothesis that **lack of internal mobility** causes top talent to look elsewhere.

### 2. The "Economic Pressure" Features
These test if the employee feels **undervalued compared to their experience level.**

* **Income per Year of Experience:** `monthly_income / total_working_years`
    * **Why:** A "Level 3" employee with 15 years of experience earning the same as a "Level 3" with 5 years will feel underpaid.
    * **Impact:** Highlights **pay inequity** and "experience-to-reward" frustration.
* **Hike vs. Performance Gap:** `percent_salary_hike - performance_rating` (requires normalization)
    * **Why:** If an employee has a "High" performance rating but a "Low" salary hike, they feel exploited.
    * **Impact:** Strong indicator of **disengagement** due to perceived unfairness.

### 3. The "Work-Life Friction" Features
These test the hypothesis that **physical and mental burnout** drives resignation.

* **Commute Strain:** `distance_from_home_km * (5 - remote_work_days_per_week)`
    * **Why:** 20km isn't bad if you work from home 4 days a week. It’s exhausting if you commute every day.
    * **Impact:** Identifies employees at risk of **physical burnout** and helps HR suggest "Remote Work" as a retention tool.
* **Total Overtime Impact:** `overtime_hours_per_week / total_working_years` (or simply a flag for `overtime_paid_eligible` AND high `overtime_hours`).
    * **Why:** Chronic overtime is the #1 killer of work-life balance.

### 4. The "Social & Growth" Features
These test the **quality of the work environment.**

* **Manager-Satisfaction Delta:** `manager_rating - job_satisfaction`
    * **Why:** There is a famous saying: *"Employees don't quit jobs; they quit managers."*
    * **Impact:** If the manager rating is high but satisfaction is low, the problem is the **workload**. If satisfaction is high but the manager rating is low, the problem is **the boss**.
* **Promotion Velocity:** `years_at_company / (promotions_last_5years + 1)`
    * **Why:** How fast is this person moving up the ladder? 
    * **Impact:** Tests if **career "velocity"** keeps people at the company.

---

### Summary Table for your Presentation

| Feature Name | Business Logic | Primary Hypothesis |
| :--- | :--- | :--- |
| **Job Hopping Index** | Are they a "flight risk" by nature? | Historical behavior predicts future behavior. |
| **Commute Strain** | Is the office visit worth the drive? | Physical exhaustion leads to 90-day attrition. |
| **Income-to-Experience** | Is the salary "fair" for their age/skills? | Financial dissatisfaction is the primary motivator for "Quiet Quitting." |
| **Stagnation Ratio** | Is the career path "clogged"? | High performers leave when they stop growing. |

### Expert Suggestion: The "Loyalty Flag"
Create a Boolean (True/False) feature called **`Is_Vulnerable`**:
* `True` if `years_since_last_promotion > 3` AND `performance_rating >= 4`.
* **Why?** These are your **"Star" employees who are being ignored.** From a consultant's view, this is the group you must save first to prevent loss of institutional knowledge.

Which of these hypotheses do you think is the biggest problem at the company you are currently analyzing?
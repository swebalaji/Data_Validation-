# Data_Validation of Patient data in Healthcare and Life Sciences 
This project provides a robust, extensible data validation model using Pydantic v2 to validate and enrich clinical trial subject demographic data.


The model ensures that every data record is:

Accurate (valid types, required fields)

Clean (case-insensitive enums, defaults)

Validated (cross-checks like BMI)

✅ Features
subject_id must be an 8-digit or longer positive integer

sex supports "Male" / "Female" input in any case (e.g. MALE, male)

ethnicity defaults to "American" if not provided

bmi must match the expected value computed from weight and height

Auto-computed fields:

expected_bmi

bmi_category (e.g., Normal, Overweight)

📦 Tech Stack
Python 3.9+

Pydantic v2

Clean and simple to extend into FastAPI or Pandas pipelines

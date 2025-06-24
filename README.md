# Data_Validation of Patient data in Healthcare and Life Sciences Using Pydantic 
This project provides a robust, extensible data validation model using Pydantic v2 to validate and enrich clinical trial subject demographic data.



**The model ensures that every data record is:**

1) Accurate (valid types, required fields)

2) Clean (case-insensitive enums, defaults)

3) Validated (cross-checks like BMI)



**✅ Features**

1) subject_id must be an 8-digit or longer positive integer

2) sex supports "Male" / "Female" input in any case (e.g. MALE, male)

3) ethnicity defaults to "American" if not provided

4) bmi must match the expected value computed from weight and height

**Auto-computed fields:**

1) expected_bmi

2) bmi_category (e.g., Normal, Overweight)

**📦 Tech Stack**

-- Python 3.9+

-- Pydantic v2

-- Clean and simple to extend into FastAPI or Pandas pipelines

**📦 Sample Input**

from model import Demographics

data = {
    "subject_id": 10011004,
    "age": 33,
    "sex": "female",
    "race": "Japanese",
    "weight_kg": 51,
    "height_cm": 155.5,
    "bmi": 21.4
}

demo = Demographics(**data)
print(demo.model_dump())


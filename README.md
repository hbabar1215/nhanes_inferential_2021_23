## NHANES 2021-2023 Inferential Analytics Assignment
In this assignment, we used NHANES data to perform basic inferential statistics using Python in Google Colab. We explored relationships and differences in health metrics and demographic variables, utilizing the skills learned in class to answer key questions about the dataset. 

NHANES Data: [NHANES Data](https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2021-2023)

**Data Preparation**: To start, we used the following NHANES variables for analysis:

- Marital Status (DMDMARTZ) - categorical, needs recoding (married or not married).
- Education Level (DMDEDUC2) - categorical, needs recoding (bachelor’s or higher vs. less than bachelor’s).
- Age in Years (RIDAGEYR) - continuous.
- Systolic Blood Pressure (BPXOSY3) - continuous.
- Diastolic Blood Pressure (BPXODI3) - continuous.
- Vitamin D Lab Interpretation (LBDVD2LC) - categorical, two levels.
- Hepatitis B Lab Antibodies (LBXHBS) - categorical, needs recoding to two levels.
- Weak/Failing Kidneys (KIQ022) - categorical, can be treated as two levels.
- Minutes of Sedentary Behavior (PAD680) - continuous, needs cleaning (remove values 7777, 9999, and null).
- Current Self-Reported Weight (WHD020) - continuous, needs cleaning (remove values 7777, 9999, and null).


**Question 1: "Is there an association between marital status (married or not married) and education level (bachelor’s degree or higher vs. less than a bachelor’s degree)?"**


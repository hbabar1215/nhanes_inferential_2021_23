## NHANES 2021-2023 Inferential Analytics Assignment
In this assignment, we used NHANES data to perform basic inferential statistics using Python in Google Colab. We explored relationships and differences in health metrics and demographic variables, utilizing the skills learned in class to answer key questions about the dataset. 

NHANES Data: [NHANES Data](https://wwwn.cdc.gov/nchs/nhanes/continuousnhanes/default.aspx?Cycle=2021-2023)

**Data Preparation**: To start, we used the following NHANES variables for analysis:

- Marital Status `(DMDMARTZ)` - categorical, needs recoding (married or not married).
- Education Level `(DMDEDUC2)` - categorical, needs recoding (bachelor’s or higher vs. less than bachelor’s).
- Age in Years `(RIDAGEYR)` - continuous.
- Systolic Blood Pressure `(BPXOSY3)` - continuous.
- Diastolic Blood Pressure `(BPXODI3)` - continuous.
- Vitamin D Lab Interpretation `(LBDVD2LC)` - categorical, two levels.
- Hepatitis B Lab Antibodies `(LBXHBS)` - categorical, needs recoding to two levels.
- Weak/Failing Kidneys `(KIQ022)` - categorical, can be treated as two levels.
- Minutes of Sedentary Behavior `(PAD680)` - continuous, needs cleaning (remove values 7777, 9999, and null).
- Current Self-Reported Weight `(WHD020)` - continuous, needs cleaning (remove values 7777, 9999, and null).


**Question 1: Is there an association between marital status (married or not married) and education level (bachelor’s degree or higher vs. less than a bachelor’s degree?**
- I had to clean the data first by recoding `DMDMARTZ` and `DMDEDUC2` and getting rid of NaN values. I used a **chi-square test** to determine whether there is an association between marital status and education level. The results indicated a p-value of 4.7017282148734955e-30 which is significant *(p<0.05)*. This suggests that there is an association between marital level and education level. People who are married are more likely to have a bachelor's degree or higher.

**Question 2: Is there a difference in the mean sedentary behavior time between those who are married and those who are not married?**
- First, I had to combine the PAQ and DEMO data into one table. Then I kept the `DMDMARTZ`, `PAD680`, and `marital status` columns and removed missing `PAD680` values (7777, 9999, and null) from both groups. Lastly, I completed an **independent t-test** and the mean to determine if there is a difference in mean sedentary behavior time between those who are married vs those who are not. The mean sedentary behavior time between those who are married is lower (353.29) compared to those who are not married (371.91). These results are significant *(t= -3.846, p< 0.05)* which means that married individuals spend less time sitting at school, at home, getting to and from places, or with friends including time spent sitting at a desk, traveling in a car or bus, reading, playing cards, watching television, or using a computer.

  **Question 3: How do age and marital status affect systolic blood pressure?**
- First, I had to combine the BPXO and DEMO data into one table. I kept the `RIDAGEYR` (age), `DMDMARTZ` (marital status, recoded), and `BPXOSY3` (systolic blood pressure) columns. I recoded the marital status and removed missing data. I compared the mean BP between both groups and ran an **independent t-test**. The married individuals had a mean systolic blood pressure of 122.61 while unmarried had a mean systolic blood pressure of 122.85. The results indicated no statistically significant difference between the two groups, *(t = –0.50, p = 0.616)*. This shows us that marital status does not effect systolic blood pressure.
- To see if age `RIDAGEYR` affects systolic blood, I ran a **Pearson Correlation test**. This showed a positive correlation between age and systolic blood pressure *(r = 0.365, p < 0.001)*. This tells us that as age increases, systolic blood pressure increases.

**Question 4: Is there a correlation between self-reported weight and minutes of sedentary behavior?**
- First, I had to combine WHQ and PAQ data so that I could analyze the `(WHD020)` and `(PAD680)` variables. I then merged the data to create one table consisting of both columns `(df_question4)`. I then cleaned the data to remove values 7777, 9999, null values, and missing data. I then completed a **Pearson Correlation test** to see whether there was a correlation between the two variables. The results suggested there is no correlation between self-reported weight and minutes of sedentary behavior as the Pearson correlation coefficient is 0.1560. This means that these variables dont have an effect on one another.

**Question 5: Do married women report greater feelings of tiredness or having little energy than unmarried women?**
- First I had to combine DPQ and DEMO data so I could analyze `DPQ040`(tiredness question), `DMDMARTZ` (marital status) and `RIAGENDR`(gender). Then I merged the data together to create one table that consists of the three columns. I also recoded the marital status and removed missing data. I compared the mean tiredness response to this question and ran an **independent t-test**. This showed a significant difference between the two groups *(t = –6.50, p < 0.001)*.
Married women reported lower tiredness (M = 0.86) compared to unmarried women (M = 1.09) in this sample which I found surprising. 

## Python vs. R 
I liked using Python more for this assignment as we've been using it since the beginning of the year. I have more experience with it. R was a bit confusing due to the syntax and the way commands are called. Additionally, for number 5 I there was a small difference in the number of unmarried people. When using Python I got 1416 but when using R I got 1418 unmarried people. This might be due to the way data is cleaned in both languages. However, since R is mostly utilized in sciences for data analysis, I would like to become more proficient at using it. With more practice I believe R will become easier to use, but for now I prefer Python.
  

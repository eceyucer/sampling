# Assignment: Questionnaire Design and Sample Evaluation

## Requirements

The goal of this assignment is to practice developing and evaluating sampling materials.

### Part A - Survey Design:

Select one of the scenarios below and design a survey to meet the need(s) outlined in the prompt.

1.	In two to three sentences, describe the purpose of your survey
2.	Describe your target population, sampling frame, sampling units, and overall sampling strategy.
3.	Write a 5-10 question survey to address your chosen scenario below.

##### Scenarios
1.	You work in the Human Resources Department at a large tech company. Over the past few months, the company has been experiencing a high turnover rate across many of its departments, specifically within the entry- and lower-level positions. The company wishes to understand why this turnover is happening, and what changes need to occur to improve employee satisfaction.
2.	You work for a Canadian national political party during a federal election. Throughout the campaign period, your party has seen relatively high approval ratings, but an opposing party is also polling favorably and may still have a chance to win the election. You are one month away from the election and you want to understand what voters want from your party and its leader in order to maintain your lead and eventually win the election.
3.	You are a student researcher in the sociology department at the University of Toronto. You are working on a research project that concerns the relationship between music taste and age. This involves both comparisons between different people of different ages and comparisons of the same individual at different ages during their lifetime. You wish to understand to what extent age influences music taste, specifically as it relates to perceptions of popular music. Your results will be written into an academic paper that you hope to publish.

### Part B - Survey Evaluation:

For the **Canadian General Social Survey on Giving, Volunteering, and Participating, 2018 (cycle 33)**, conducted by Statistics Canada find any and all available documentation for the data gathered and identify and describe the survey features indicated below. (https://www23.statcan.gc.ca/imdb/p2SV.pl?Function=getSurvey&Id=796234)

1. Sample type
2. Sample size
3. Target population
4. Sampling frame
5. Survey mode(s) 
6. Timeline
7. Response rate
8. Weights
9. Data processing
10. Cleaning, imputation, etc
11. Sources of error
12. Limitations, known biases, etc
13. Link to documentation and any additional sources used


# Your Changes

## Part A - Survey Design: 

The number of your chosen topic: `#2`

Describe the purpose of your survey:
```
The purpose of this survey is to understand the desires of voters from the political party and its leaders. The goal is to use this information to refine campaign messaging and policy focus in order to maintain our lead and eventually win the election.
```

Describe your target population, sampling frame, sampling units, and observational units:
```
Target population: eligible Canadian voters across all provinces and territories
Sampling frame: list of registered voters obtained from Elections Canada
Sampling unit: each individual registered voter
Observational units: each individual registered voter who respond to the survey
Sampling strategy: Stratified random sampling to ensure that we have a proportional representation from key demographic groups such as age, gender, region and political affiliation to have a balanced picture of national registered voter's sentiments.
```

Your 5-10 question survey:
```
1. How old are you? [Open-ended numerical input]
2. What is your gender? (e.g., woman, genderqueer, two-spirit) [open-ended, adapted from Beischel et al., 2023]
    Beischel, W. J., Schudson, Z. C., Hoskin, R. A., & Van Anders, S. M. (2023). The gender/sex 3×3: Measuring and categorizing gender/sex beyond binaries. Psychology of Sexual Orientation and Gender Diversity, 10(3), 355–372. https://doi.org/10.1037/sgd0000558
3. What's your postal code? [open-ended]
4. How likely are you to vote in the upcoming federal election? [forced choice with an unsure option]
    a. very likely
    b. somewhat likely
    c. not very likely
    d. not at all likely
    e. unsure
5. Which federal political party do you currently support the most? [forced choice with an unsure option]
    a. liberal party
    b. conservative party
    c. new democratic party
    d. bloc quebecois
    e. green party
    f. people's party of canada
    g. other (please specify): ________
    h. undecided
6. What are the top three issues that will influence your vote in this election? [select all that apply with an other option where respondents can specify]
    - climate change/environment
    - healthcare
    - Indigenous reconciliation
    - housing affordability
    - public safety
    - education
    - taxes
    - economy
    - other (please specify): _______
7. What qualities do you most value in a party leader? [select all that apply]
    - decisiveness
    - experience
    - communication skills
    - transparancy
    - integrity
    - relatability
    - other (please specify): ________
8. Do you feel our party's platform addresses your personal and community needs? [forced choice with not sure]
    a. yes
    b. somewhat
    c. no
    d. not sure
9. What policy or issue do you feel our party should focus on more in the remaining weeks of the campaign? [open-ended]
10. Please share any additional comments or suggestions for our party's campign: [open-ended]
```

## Part B - Survey Evaluation:

Identify and describe survey features:

```
1. Sample type: stratified design employing probability sampling, where the stratification is done at the province/census metropolitan area (CMA) level (stratas) and information is collected from one randomly selected household member aged 15 or older
2. Sample size: 16,760 (41.9% of 40,000 contacted households) individuals aged 15 or older
3. Target population: All persons 15 years of age and older living in the ten provinces of Canada, excluding full-time residents of institutions
4. Sampling frame: landline and cellular telephone numbers from the Census and administrative sources with Statistics Canada's dwelling frame
5. Survey mode(s): electronic quesionnaire of CATI (computer assisted telephone interviewing) 
6. Timeline: September to December 2018
7. Response rate: 41.9% response rate
8. Weights: number of persons represented by one respondent, reflecting the properties of people with the same characteristics
 weighted by WGHT_PER: which is the basic weighting factor for analysis at the person level, i.e. to calculate estimates of the number of persons (non-institutionalized and aged 15 or over) having one or several given characteristics. Also, bootstrap weights have been created for the purpose of design-based variance estimation.
9. Data processing: coding of responses to questions with "Other - specify" answer category, editing of data (age, sex, family relationships) to ensure validity, coding of category responses, imputation of data, calculation of derived variables, weighting and variance estimation
10. Cleaning, imputation, etc: donor imputation using nearest neighbor scoring. This was achieved through comparing certain characteristics on each record with item or partial non response with the characteristics on all donor records, and when a characteristic was the same on the donor record and the recipient record, the donor's score increased -- the highest score was deemed the nearest donor and was chosen to fill in the missing information of the non respondent. If donor imputation could not be used, a mean imputation among a pool of donors was used. 
11. Sources of error: sampling error was measured via bootstrapping. Non-sampling errors:
    coverage error: households without phones were excluded
    non-response bias: at household and individual level
    response error: inaccurate or incomplete answers
    processing error: inaccuracies during coding the data or editing
12. Limitations, known biases, etc:
    coverage bias (as listed above)
    non-response bias: adjusted using income, household structure data for modelling
13. Link to documentation and any additional sources used:
    For SPSE data processing: https://www150.statcan.gc.ca/n1/pub/75-005-m/75-005-m2019001-eng.htm
    How variables were coded: https://www23.statcan.gc.ca/imdb/p2SV.pl?Function=getSurvVariableList&Id=796234
    The survey: https://www23.statcan.gc.ca/imdb/p2SV.pl?Function=getSurvey&Id=796234 
```

## Rubric

-	All required components are present and complete **Complete / Incomplete**
-	Choice of sampling strategy for Part A is justified and related to survey purpose **Complete / Incomplete**
-	Information for Part B is complete and correct **Complete / Incomplete**

## Submission Information

🚨 **Please review our [Assignment Submission Guide](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md)** 🚨 for detailed instructions on how to format, branch, and submit your work. Following these guidelines is crucial for your submissions to be evaluated correctly.

### Submission Parameters:
* Submission Due Date: `23:59 - 18/04/2025`
* The branch name for your repo should be: `assignment-2`
* What to submit for this assignment:
    * This markdown file (a2_survey_design_and_evaluation.md) should be populated and should be the only change in your pull request.
* What the pull request link should look like for this assignment: `https://github.com/<your_github_username>/sampling/pull/<pr_id>`
    * Open a private window in your browser. Copy and paste the link to your pull request into the address bar. Make sure you can see your pull request properly. This helps the technical facilitator and learning support staff review your submission easily.

Checklist:
- [ ] Create a branch called `assignment-2`.
- [ ] Ensure that the repository is public.
- [ ] Review [the PR description guidelines](https://github.com/UofT-DSI/onboarding/blob/main/onboarding_documents/submissions.md#guidelines-for-pull-request-descriptions) and adhere to them.
- [ ] Verify that the link is accessible in a private browser window.

If you encounter any difficulties or have questions, please don't hesitate to reach out to our team via the help channel in Slack. Our Technical Facilitators and Learning Support staff are here to help you navigate any challenges.

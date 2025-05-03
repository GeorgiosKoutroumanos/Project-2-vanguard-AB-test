# Project-2-vanguard-AB-test

## Overview
This project analyzes the results of an A/B test conducted on the Vanguard online platform. The goal is to determine the effectiveness of a new online process compared to the existing one. The analysis focuses on key performance indicators (KPIs) such as completion rate, time spent, and error rate.

## Data Sources
The project utilizes the following datasets:
*   `df_final_demo.txt`: Client demographic information.
*   `df_final_experiment_clients.txt`: Assignment of clients to either the Test or Control variation.
*   `df_final_web_data_pt_1.txt`: Web activity data (part 1).
*   `df_final_web_data_pt_2.txt`: Web activity data (part 2).

## Dependencies
The analysis is performed using Python and the following libraries:
*   pandas
*   matplotlib
*   seaborn
*   numpy
*   scipy.stats
*   datetime

## Data Cleaning and Preprocessing
The following steps are performed to clean and prepare the data for analysis:
1.  Load the datasets using pandas.
2.  Concatenate the two web activity data files (`df_final_web_data_pt_1.txt` and `df_final_web_data_pt_2.txt`) into a single dataframe.
3.  Merge the client demographic data (`df_final_demo.txt`) with the variation assignment data (`df_final_experiment_clients.txt`) based on the `client_id`.
4.  Merge the combined web activity data with the merged demographic and variation data.
5.  Handle missing values by filling with the mean for numerical columns, 'U' for gender, and 'Unknown' for variation.
6.  Remove duplicate rows.

## Analysis
The analysis involves the following steps:
1.  Define primary client attributes (age, tenure, number of accounts, balance, calls, logins) and calculate summary statistics.
2.  Determine the number of unique clients in each variation group (Test, Control, Unknown).
3.  Explore client demographics, including age, tenure, account balances, and digital engagement.
4.  Examine correlations between client tenure, logins, number of accounts, and balance.
5.  Analyze gender distribution within each variation group.
6.  Assess age distribution within each variation group.
7.  Create a membership level category based on account balance.
8.  Analyze KPIs:
    *   **Completion Rate:** Calculate the percentage of clients who reach the 'confirm' step.
    *   **Time Spent on Each Step:** Calculate the average duration users spend on each step, using both all users and grouping by 'test' and 'control'.
    *   **Error Rates:** Identify steps where users go back to a previous step, indicating confusion or an error.
9.   Perform hypothesis testing on completion rate, average time spent, and balances.
10. Analyze the Average time spend excluding the outliers

## Key Variables
* client_id: Unique identifier for each client.
* visitor_id: Unique identifier for each visitor.
* visit_id: Unique identifier for each visit.
* process_step: Step in the online process.
* date_time: Timestamp of the event.
* clnt_tenure_yr: Client tenure in years.
* clnt_tenure_mnth: Client tenure in months.
* clnt_age: Client age.
* gendr: Client gender.
* num_accts: Number of accounts held by the client.
* bal: Account balance.
* calls_6_mnth: Number of calls made in the last 6 months.
* logons_6_mnth: Number of logons in the last 6 months.
* Variation: Test or Control group assignment.
*membership_level: Categorie to classify the clients based in their 'bal'

## Key Findings:
*   The code examines completion rates under different definitions (reaching 'confirm' vs. completing all steps in the correct order)
*   T-tests were used to compare the average time spent and to conclude if a specific variation have a major performance than others in general terms (ignoring the outliers)
*   The total balance for each variation was analyzed to determine if there's any difference between the amounts in average
*   There's a section analyzing the influence of average time spen in each process by generation (Baby bommers, Millenials, etc)
  
## Next Steps
*   Refine error rate definition and analysis.
*   Perform additional analysis to identify factors that influence completion rate, time spent, and error rate.
*   Develop recommendations for improving the online process.
*  Use of external dashboard software (Tableau, etc)
*  
## Presentation
https://docs.google.com/presentation/d/1g13gdJfLgCv-3AJnuT96HrTF1vNJwC0W8Rhmx0kDUyM/edit?slide=id.p#slide=id.p

## Tableau Dashboard
(https://public.tableau.com/app/profile/georgios.koutroumanos1227/viz/Dashboard_Project2_17461209245410/Dashboard1)



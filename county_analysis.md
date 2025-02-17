<h1 align="center">Analysis of Mortality and Incarceration Risk Across Demographic Variables</h1>

<h3 align="center">Introduction</h3>
I conducted this analysis as part of a 3-hour long Data Challenge.<br><br>

The primary goal of this challenge is to analyze two datasets and prepare a cross-tabulation report that can help the county understand the relationship between various demographics (age, gender, etc) and the probability a person is at risk of death and incarceration.

<h3 align="center">Datasets</h3>
As part of this challenge, I was provided two datasets relating to one of the county’s welfare intervention programs:

1. **Demographics Dataset:** Contains demographics variables (age, sex, race, history of opiod use, etc) for each person 
2. **Risk Scores Dataset:** Includes out-of-sample risk scores for two outcomes (mortality and incarceration). These scores represent the estimated probability of a person being at risk of death and incarceration


<h3 align="center">Task and Methodology</h3>

I was tasked to analyze both datasets and create two cross-tabulations reports (one for mortality and one for incarceration) showing for each demographic category, the:

- **Population %:** The percentage of the population in the dataset with the variable
- **Avg Risk Score:** The average risk score for each category
- **Top 1%, 5% and 10%:** The average risk score for the top 1%, 5%, 10% highest risk scores within the category


The goal of the cross tabulation is to
1. Understand the demographic breakdown of the groups an intervention would be targeted towards if the model is used, and
2. Understand how risk level varies across groups (i.e. gender or age range or people with a history of opioid use).

<h3 align="center">Code</h3>

```python
import pandas as pd

def calculate_statistics(outcome, categorical_features_list):
    
    """
    Calculates statistics for categorical demographic features based on a specified outcome, specifically:
    1. The percentage of the total population for each category within a categorical feature.
    2. The average predicted risk score for each category.
    3. The percentage breakdown of the riskiest population at different thresholds (Top 1%, 5%, and 10% risk levels).
    
    Parameters:
    ----------
    outcome : str
        The outcome variable to analyze. Must be one of:
        - 'ONE_YEAR_JAIL'
        - 'ONE_YEAR_MORTALITY'

    categorical_features_list : list of str
        A list of categorical column names

    Returns:
    -------
    pd.DataFrame
        A formatted DataFrame containing:
        - 'Population %': Percentage of the total dataset belonging to each category.
        - 'Avg Risk Score': The average predicted probability of the specified outcome for each category.
        - 'Top_1%_score', 'Top_5%_score', 'Top_10%_score': Categorical breakdown of top 1%, 5%, and 10% of riskiest populations.
        - 'feature': The categorical feature being analyzed.
        - 'category': The specific category within the feature.
    
    """  

    # Sanity Check: Ensure that the outcome passed is one of the outcomes we have probabilities for in our dataset
    if outcome == 'ONE_YEAR_JAIL':
        predic_prob = 'YHAT_JAIL'
    elif outcome == 'ONE_YEAR_MORTALITY':
        predic_prob = 'YHAT_MORTALITY'
    # if the outcome passed to the function is incorrect, print a message to redict user
    else:
        print('Outcome must be either ONE_YEAR_JAIL or ONE_YEAR_MORTALITY. Please specify correct outcome')


    # Create an empty dataframe to store final result
    statistics = pd.DataFrame()

    top_N = [0.01, 0.05, 0.1] #1%, 5%, and 10%

    # Given that we need to calculate statistics based on all features, we loop through them
    for feature in categorical_features_list:

        # 1. For each feature, caculate the % of the population
        perc = merged_df[feature].value_counts() /len(merged_df)
        perc.name = "Population %"
        perc = perc.to_frame().reset_index()   # Convert series to dataframe
   
        
        # 2. Calculate average risk score for each categorical group
        avg_risk = merged_df.groupby(feature).agg({predic_prob:'mean'}) 
        avg_risk = avg_risk.reset_index().rename(columns={predic_prob: "Avg Risk Score"})

        
        # Calculate top N% riskiest clients (based on their predicted probability of the relevant outcome)
        risk_score = []
        for n in top_N:

            # First, we extract the population that is at the n% risk level  (1, 5 or 10% risk level)
            # i.e the population for which the predicted probability is at the top 1%
            riskiest_pop = merged_df[merged_df[predic_prob] > merged_df[predic_prob].quantile(1-n)]

            # Second, we calculate the demographic breakdown for that population
            riskiest_by_demographics = riskiest_pop[feature].value_counts() /len(riskiest_pop)
            riskiest_by_demographics.name = f"Top_{int(n * 100)}%_score"

            risk_score.append(riskiest_by_demographics)
        
        # Concatenate the list w/ top N scores and convert to pandas frame
        risk_score = pd.concat(risk_score, axis=1).reset_index()

        # Here, we combine all three statistics (% of Population, Avg, and Top N Scores)
        feature_stats = perc.merge(avg_risk, on = feature).merge(risk_score, on = feature, how = 'outer')
            
        # Create a category and feature columns
        feature_stats['feature'] = feature
        feature_stats['category'] = feature_stats[feature]

        # drop the feature specific column (i.e Legal_sex, or race etc...) not the "feature" column
        # this is to enable concatenation with the next feature
        feature_stats = feature_stats.drop(columns = {feature})

        statistics = pd.concat([feature_stats, statistics], axis=0)

    # Formatting
    # Multiply by 100 and format to two decimal places with a '%' sign
    cols_to_be_formatted = ["Population %", "Avg Risk Score", "Top_1%_score", "Top_5%_score", "Top_10%_score"]
    statistics[cols_to_be_formatted ] = statistics[cols_to_be_formatted].map(lambda x: f"{x * 100:.2f}%" if pd.notnull(x) else "NaN")


    return statistics




def write_to_csv(statistics, file_name):

    """
    Parameters:
    ----------
    - statistics: The data structure to capture and format into an excel sheet.
    - file_name: Desired File Name
    """

    # this is the function to output your crosstabs in a .csv
    file_name = str(file_name) + '.csv'
    statistics.to_csv(file_name)
 
        
# Main function structure
if __name__ =="__main__":
    # Importing files
    scores = pd.read_csv('scores.csv')
    pop_features = pd.read_csv('pop_features.csv')

    # Merge the two datasets so we have access to scores, features, and outcomes in one df
    merged_df = pop_features.merge(scores, how = 'inner', on=['CLIENT_ID', 'EPISODE_DATE'])

    # Define the outcomes and features you are interested in analyzing.
    outcomes = ['ONE_YEAR_MORTALITY', 'ONE_YEAR_JAIL']
    features = ['AGE_BUCKET', 'LEGAL_SEX', 'RACE', 'OPIOID_PRE']

    
    for outcome in outcomes:
        """ 
        The `calculate_statistics` function is expected to perform all necessary
         statistical calculations for the given outcome. This includes determining
         the average outcome scores, population percentages, and scores within the top
         percentages of the population for this outcome.
        
        """
        statistics = calculate_statistics(outcome=outcome, categorical_features_list=features)
        

        # write each outcome's statistics to a CSV file.
        filename = str(outcome)
        write_to_csv(statistics, filename)
```

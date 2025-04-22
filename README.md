# MavenRail Ticket Refund Prediction

## Project Overview
This project analyzes train ticket sales data from the UK National Rail services to predict when customers are likely to request refunds. Using exploratory data analysis and regression modeling, the project aims to provide insights into refund patterns and build a predictive model to help railway operators anticipate refund requests.

## Dataset Description
The MavenRail dataset contains train ticket sales with journey records of customers using National Rail services in the UK over a four-month period (January-April 2024). The dataset includes:

- Ticket purchase information (payment method, railcard usage, ticket class, ticket type, price)
- Journey details (departure station, arrival station, departure time, scheduled arrival, actual arrival)
- Journey status (on time, delayed) and reasons for delay
- Refund request information

The dataset contains 31,645 records with 13 columns, providing comprehensive information about rail journeys and customer behavior.

## Methodology

### Data Preprocessing
- Handled missing values in 'Railcard', 'Reason.for.Delay' and 'Actual.Arrival' columns
- Removed records with timestamp anomalies (3% of data)
- Transformed datetime columns to appropriate formats
- Created derived features like departure time and delay duration

### Exploratory Data Analysis
- Analyzed categorical features (payment methods, ticket classes, journey status)
- Identified peak travel times (8:00 and 18:00, aligning with rush hours)
- Determined price distribution patterns (75% of tickets priced at or below £35)
- Identified major railway stations (Birmingham New Street, Manchester Piccadilly, Liverpool Lime Street)
- Analyzed station activity patterns throughout the day using heatmaps
- Investigated relationship between ticket prices and refund requests

### Model Development
- Implemented a univariate logistic regression model using 'MediumPrice' as predictor
- Developed a multivariate logistic regression model incorporating various features
- Achieved 93% accuracy on the test dataset
- Evaluated model performance using confusion matrix to understand false positives and false negatives

## Key Findings
- Standard tickets comprise 90% of sales, with only 10% being First Class
- 86% of journeys were on time, and 96.5% of sales did not lead to refund requests
- Customers with medium-priced tickets (£10-£30) have a higher probability of requesting refunds
- When a customer paid £5, there is a 25% probability they will request a refund
- When a customer paid £25, there is a 32% probability they will request a refund
- The multivariate model showed strong predictive power but tended to be biased toward predicting "No Refund"

## Implementation
The analysis was performed using Python with the following libraries:
- pandas and numpy for data manipulation
- matplotlib and seaborn for data visualization
- scikit-learn for machine learning models and data preprocessing

## Usage
The trained model can be used to:
- Predict the likelihood of refund requests for new ticket sales
- Help railway operators anticipate refund patterns
- Guide pricing strategies to optimize customer satisfaction and revenue

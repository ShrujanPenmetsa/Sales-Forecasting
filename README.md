# Project Overview
This project aims to forecast YoY reported sales for leading restaurant chains by integrating transactional, spend, and panelist data with advanced feature engineering and statistical modeling. Additionally, the project includes NLP-based customer sentiment analysis to extract qualitative insights from 30K+ online reviews.

# Feature Engineering

Due to non-uniform date intervals across restaurants for the Reported Sales YoY, raw data was aggregated to match each restaurant's specific reporting periods (as defined in the Reported Numbers sheet).

Key engineered features include:

    Transaction per Panelist = Total Transactions / Total Panel Size

    Spend per Panelist = Total Spend / Total Panel Size

    Spend per Transaction = Total Spend / Total Transactions

These were used to derive the following year-over-year (YoY) change metrics:

    YoY change in Transaction per Panelist

    YoY change in Spend per Panelist

    YoY change in Spend per Transaction

Panel statistics were used to normalize metrics and account for varying panel sizes across time.

# Modeling Strategy

    Built individual linear regression models per restaurant due to limited data points.

    Prioritized interpretability using p-values and correlation analysis.

    Models were evaluated using Adjusted R² and Mean Squared Error (MSE).

    Found that:

        Transaction per Panelist YoY and Spend per Panelist YoY were consistently strong predictors.

        Spend per Transaction YoY lacked predictive power.

# Sentiment Analysis

    Analyzed customer reviews using:

        TextBlob for initial sentiment scoring

        RoBERTa (Hugging Face) for context-aware sentiment classification

    Aggregated sentiment polarity and labeled reviews as positive/negative.

    Created word clouds to extract common themes across restaurants, identifying drivers of satisfaction and dissatisfaction (e.g., food quality, wait time, service).

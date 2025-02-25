# airbnb-listing-analysis

<a target="_blank" href="https://cookiecutter-data-science.drivendata.org/">
    <img src="https://img.shields.io/badge/CCDS-Project%20template-328F97?logo=cookiecutter" />
</a>

Analyze AirBnB listings in Paris to determine the impact of recent regulations.

## Objectives

### Objective 1: Profile & QA the data

* **Task 1: Import/Open the `Listings.csv` file**
    * Read the `Listings.csv` file into a Pandas DataFrame.
* **Task 2: Cast any date columns as a datetime format**
    * Convert the 'host_since' column to datetime format.
* **Task 3: Filter the data down to rows where the city is Paris, and keep only the columns ‘host_since’, ‘neighbourhood’, ‘city’, ‘accommodates’, and ‘price’**
    * Filter the DataFrame to include only rows where the 'city' column is 'Paris'.
    * Select and retain only the specified columns.
* **Task 4: QA the Paris listings data: check for missing values, and calculate the minimum, maximum, and average for each numeric field**
    * Check for missing values in the filtered DataFrame.
    * Calculate the minimum, maximum, and average values for the 'accommodates' and 'price' columns.

### Objective 2: Prepare the data for visualization

* **Task 5: Create a table named `paris_listings_neighbourhood` that groups Paris listings by 'neighbourhood' and calculates the mean price (sorted low to high)**
    * Group the filtered DataFrame by 'neighbourhood'.
    * Calculate the mean price for each neighbourhood.
    * Sort the results by mean price in ascending order.
* **Task 6: Create a table named `paris_listings_accomodations`, filter down to the most expensive neighborhood, group by the ‘accommodations’ column, and add the mean price for each value of ‘accommodates’ (sorted low to high)**
    * Find the most expensive neighbourhood from the previous created table.
    * Filter the paris listings data to only include the most expensive neighbourhood.
    * Group the filtered DataFrame by 'accommodates'.
    * Calculate the mean price for each 'accommodates' value.
    * Sort the results by 'accommodates' in ascending order.
* **Task 7: Create a table called `paris_listings_over_time` grouped by the ‘host_since’ year, and calculate the average price and count of rows representing the number of new hosts**
    * Extract the year from the 'host_since' column.
    * Group the DataFrame by the extracted year.
    * Calculate the average price and the count of rows (new hosts) for each year.

### Objective 3: Visualize the data and summarize findings

* **Task 8: Create a horizontal bar chart of the average price by neighborhood in Paris, and make sure to add a title and change axis labels as needed**
    * Use the `paris_listings_neighbourhood` DataFrame to create a horizontal bar chart.
    * Add a title and appropriate axis labels.
* **Task 9: Create a horizontal bar chart of the average price by ‘accommodates’ in Paris’ most expensive neighborhood, and make sure to add a title and change axis labels as needed**
    * Use the `paris_listings_accomodations` DataFrame to create a horizontal bar chart.
    * Add a title and appropriate axis labels.
* **Task 10: Create two line charts: one showing the count of new hosts over time, and one showing average price. Set the y-axis limit to 0, add a title, and change axis labels as needed**
    * Use the `paris_listings_over_time` DataFrame to create two line charts.
    * Set the y-axis limit to 0 for both charts.
    * Add titles and appropriate axis labels.
* **Task 11: Based on your findings, what insights do you have about the impact of the 2015 regulations on new hosts and prices?**
    * Analyze the line charts to determine the impact of the 2015 regulations.
* **Task 12: BONUS: Create a dual axis line chart to show both new hosts and average price over time**
    * Create a dual axis line chart from the paris_listings_over_time table.

### Final Step

* **Final Project Question:**
    * Which neighborhood in Paris has the highest average AirBnB listing price?


## Project Organization

```
├── LICENSE            <- Open-source license if one is chosen
├── Makefile           <- Makefile with convenience commands like `make data` or `make train`
├── README.md          <- The top-level README for developers using this project.
├── data
│   ├── external       <- Data from third party sources.
│   ├── interim        <- Intermediate data that has been transformed.
│   ├── processed      <- The final, canonical data sets for modeling.
│   └── raw            <- The original, immutable data dump.
│
├── docs               <- A default mkdocs project; see www.mkdocs.org for details
│
├── models             <- Trained and serialized models, model predictions, or model summaries
│
├── notebooks          <- Jupyter notebooks. Naming convention is a number (for ordering),
│                         the creator's initials, and a short `-` delimited description, e.g.
│                         `1.0-jqp-initial-data-exploration`.
│
├── pyproject.toml     <- Project configuration file with package metadata for 
│                         airbnb-listing-analysis and configuration for tools like black
│
├── references         <- Data dictionaries, manuals, and all other explanatory materials.
│
├── reports            <- Generated analysis as HTML, PDF, LaTeX, etc.
│   └── figures        <- Generated graphics and figures to be used in reporting
│
├── requirements.txt   <- The requirements file for reproducing the analysis environment, e.g.
│                         generated with `pip freeze > requirements.txt`
│
├── setup.cfg          <- Configuration file for flake8
│
└── airbnb-listing-analysis   <- Source code for use in this project.
    │
    ├── __init__.py             <- Makes airbnb-listing-analysis a Python module
    │
    ├── config.py               <- Store useful variables and configuration
    │
    ├── dataset.py              <- Scripts to download or generate data
    │
    ├── features.py             <- Code to create features for modeling
    │
    ├── modeling                
    │   ├── __init__.py 
    │   ├── predict.py          <- Code to run model inference with trained models          
    │   └── train.py            <- Code to train models
    │
    └── plots.py                <- Code to create visualizations
```

--------


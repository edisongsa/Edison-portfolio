# Impact of El Niño Events on Wildfires: A Data Analysis Study

## Introduction
The objective of this project is to analyze the impact of El Niño events on the occurrence and severity of wildfires. El Niño is a climate phenomenon characterized by warming of the ocean surface temperatures in the central and eastern tropical Pacific. It is known to influence weather patterns worldwide, potentially affecting wildfire conditions. By analyzing historical wildfire data in conjunction with El Niño index data, this study aims to determine if there is a significant increase in the number of wildfires during El Niño years.

## Data Collection
Two datasets will be used for this analysis:
- Wildfire Data: The dataset contains information on the number of fires and acres burned from 1983 to 2022. It includes variables such as the year, number of fires, and acres burned.
- El Niño Index Data: The dataset includes information on El Niño events, including the year, start ONI value, starting season, peak ONI value, and peak season. The ONI (Oceanic Niño Index) is a measure of the departure from average sea surface temperatures in the tropical Pacific.

## Data Analysis
The analysis will involve the following steps:
- Data Preprocessing: The wildfire and El Niño index datasets will be loaded into R and prepared for analysis. This includes handling missing values, converting data types, and merging the datasets based on the common year column.
- Statistical Testing: A t-test will be conducted to compare the number of fires during El Niño years and non-El Niño years. The t-test will evaluate whether there is a significant difference in the number of fires between these two groups.
- Interpretation of Results: The t-test results will be analyzed, and conclusions will be drawn based on the significance level (e.g., 0.05). If the p-value is below the significance level, it suggests a significant increase in the number of fires during El Niño events.

## Expected Outcome
The project aims to determine whether there is a statistically significant association between El Niño events and an increase in wildfires. The findings will contribute to our understanding of the relationship between climate patterns and wildfire occurrences. If a significant association is identified, it may have implications for wildfire management and preparedness during El Niño years.

## Limitations and Future Scope
It is important to acknowledge that this analysis has certain limitations. The study focuses on the number of fires and does not consider other factors that may influence wildfire occurrences, such as human activity or local environmental conditions. Additionally, the analysis is based on historical data, and future climate patterns and their potential impact on wildfires may differ. Future research could incorporate additional variables and consider a more comprehensive analysis of wildfire dynamics.

By conducting this data analysis, we aim to gain insights into the relationship between El Niño events and wildfire occurrences. The results of this study can contribute to scientific understanding and inform strategies for wildfire prevention, preparedness, and response during El Niño years.

## No Installation Required
This project does not require any specific installation. The analysis will be performed using the R programming language, which is widely available and can be executed on various platforms. The code provided in this project can be run on any system with R installed. The datasets used in the analysis will be provided along with the code, ensuring easy replication and execution of the analysis.

## Observed Result
Based on the analysis, there was no significant difference in the number of fires during El Niño events.

## Conclusion
The project analyzed the relationship between El Niño events and wildfire occurrences. The findings suggest that El Niño events may not have a significant impact on the number of fires. However, it's important to note that this conclusion is based on the specific datasets and analysis approach used in this study.


Data used
Fire data https://www.nifc.gov/fire-information/statistics/wildfires
El Nino data https://mrcc.purdue.edu/mw_climate/elNino/historical.jsp

```R
# Load the required libraries
library(tidyverse)

# Read the dataset of fire occurrences
fire_data <- read.csv("fire_data.csv", stringsAsFactors = FALSE)
fire_data$Year <- as.integer(fire_data$Year)

# Read the dataset of El Niño index
nino_data <- read.csv("nino_data.csv", stringsAsFactors = FALSE)
nino_data$Year <- as.integer(substr(nino_data$Year, 1, 4))  # Extracting only the year from the combined format (e.g., "1982-83")

# Merge the datasets based on the common year column
merged_data <- merge(fire_data, nino_data, by = "Year", all.x = TRUE)

# Perform a t-test to compare the number of fires during El Niño and non-El Niño years
t_test_result <- t.test(Fires ~ !is.na(`Start ONI value`), data = merged_data)

# Display the t-test results
cat("T-test Results:\n")
cat("----------------------------\n")
cat("Null Hypothesis (H0): The number of fires is the same during El Niño and non-El Niño years.\n")
cat("Alternate Hypothesis (HA): The number of fires is significantly different during El Niño and non-El Niño years.\n")
cat("T-statistic:", t_test_result$statistic, "\n")
cat("P-value:", t_test_result$p.value, "\n")

# Check if the p-value is less than the significance level (e.g., 0.05) to determine significance
if (t_test

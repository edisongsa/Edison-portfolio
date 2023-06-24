# Edison-portfolio

Welcome to the **Edison-portfolio** repository! This project serves as a collection of my data analytics projects, showcasing my skills and expertise in the field. It is designed to provide potential employers with insights into my capabilities and help them determine if I am a suitable candidate for their data-related positions.

## Usage

To explore the Edison-portfolio and review my data analytics projects, follow these steps:

1. Visit the portfolio website: [Edison-portfolio](https://edisongsa.github.io/Edison-portfolio/)

2. Browse through the different sections and projects to gain an understanding of my skills, methodologies, and achievements.

3. Each project will have a description explaining the problem statement, data used, analysis techniques applied, and key findings or insights obtained.

4. Feel free to review the code and documentation for each project. They are provided alongside the project descriptions, allowing you to delve deeper into the technical aspects if desired.

5. If you have any questions or would like to discuss any specific project, please contact me using the contact information provided on the portfolio website.

## No Installation Required

The Edison-portfolio does not require any installation. It is a static website hosted on a web server and can be accessed directly through the provided link.

## License, Credits, and Contributions

Since there is no code or software installation involved in this portfolio, there is no specific licensing, credits, or contribution guidelines to mention. The projects showcased in the portfolio are representative of my personal work and are not open for direct contributions.

However, if you are interested in collaborating or have any suggestions or feedback, please reach out to me using the contact information provided on the portfolio 
website. I am open to discussions and potential collaborations in the data analytics field.

---

Thank you for taking the time to review my Edison-portfolio. I hope this collection of data analytics projects effectively demonstrates my skills and expertise. If you have any further inquiries or require additional information, please do not hesitate to reach out to me.


#PROJECT 1
#Impact of El Niño Events on Wildfires: A Data Analysis Study

Introduction
The objective of this project is to analyze the impact of El Niño events on the occurrence and severity of wildfires. El Niño is a climate phenomenon characterized by warming of the ocean surface temperatures in the central and eastern tropical Pacific. It is known to influence weather patterns worldwide, potentially affecting wildfire conditions. By analyzing historical wildfire data in conjunction with El Niño index data, this study aims to determine if there is a significant increase in the number of wildfires during El Niño years.

Data Collection
Two datasets will be used for this analysis:

Wildfire Data: The dataset contains information on the number of fires and acres burned from 1983 to 2022. It includes variables such as the year, number of fires, and acres burned.
El Niño Index Data: The dataset includes information on El Niño events, including the year, start ONI value, starting season, peak ONI value, and peak season. The ONI (Oceanic Niño Index) is a measure of the departure from average sea surface temperatures in the tropical Pacific.
##Data Analysis
The analysis will involve the following steps:

Data Preprocessing: The wildfire and El Niño index datasets will be loaded into R and prepared for analysis. This includes handling missing values, converting data types, and merging the datasets based on the common year column.
Statistical Testing: A t-test will be conducted to compare the number of fires during El Niño years and non-El Niño years. The t-test will evaluate whether there is a significant difference in the number of fires between these two groups.
Interpretation of Results: The t-test results will be analyzed, and conclusions will be drawn based on the significance level (e.g., 0.05). If the p-value is below the significance level, it suggests a significant increase in the number of fires during El Niño events.

Expected Outcome
The project aims to determine whether there is a statistically significant association between El Niño events and an increase in wildfires. The findings will contribute to our understanding of the relationship between climate patterns and wildfire occurrences. If a significant association is identified, it may have implications for wildfire management and preparedness during El Niño years.

Limitations and Future Scope
It is important to acknowledge that this analysis has certain limitations. The study focuses on the number of fires and does not consider other factors that may influence wildfire occurrences, such as human activity or local environmental conditions. Additionally, the analysis is based on historical data, and future climate patterns and their potential impact on wildfires may differ. Future research could incorporate additional variables and consider a more comprehensive analysis of wildfire dynamics.

By conducting this data analysis, we aim to gain insights into the relationship between El Niño events and wildfire occurrences. The results of this study can contribute to scientific understanding and inform strategies for wildfire prevention, preparedness, and response during El Niño years.


Data used
Fire data https://www.nifc.gov/fire-information/statistics/wildfires
El Nino data https://mrcc.purdue.edu/mw_climate/elNino/historical.jsp

Code:

# Load the required libraries
library(tidyverse)

# Read the dataset of fire occurrences
fire_data <- read.csv("fire_data.csv", stringsAsFactors = FALSE)
fire_data$Year <- as.integer(fire_data$Year)

# Create a dataframe for the modified nino_data
nino_data <- data.frame(
  Year = c(1982, 1991, 1997, 2015),
  Start_ONI = c(0.5, 0.6, 0.6, 0.5),
  Starting_Season = c("MAR-MAY", "MAY-JUL", "APR-JUN", "FEB-APR"),
  Peak_ONI = c(2.1, 1.6, 2.3, NA),
  Peak_Season = c("OCT-FEB", "DEC-FEB", "OCT-JAN", NA)
)

# Merge the datasets based on the common year column
merged_data <- merge(fire_data, nino_data, by = "Year", all.x = TRUE)

# Convert Fires column to numeric
merged_data$Fires <- as.numeric(gsub(",", "", merged_data$Fires))

# Create a binary variable indicating missing values in "Start ONI value"
merged_data$Missing_ONI <- is.na(merged_data$Start_ONI)

# Perform a t-test to compare the number of fires during El Niño and non-El Niño years
t_test_result <- t.test(Fires ~ Missing_ONI, data = merged_data, na.action = na.omit)

# Display the t-test results
cat("T-test Results:\n")
cat("----------------------------\n")
cat("Null Hypothesis (H0): The number of fires is the same during El Niño and non-El Niño years.\n")
cat("Alternate Hypothesis (HA): The number of fires is significantly different during El Niño and non-El Niño years.\n")
cat("T-statistic:", t_test_result$statistic, "\n")
cat("P-value:", t_test_result$p.value, "\n")

# Check if the p-value is less than the significance level (e.g., 0.05) to determine significance
if (t_test_result$p.value < 0.05) {
  cat("Conclusion: The number of fires significantly increased during El Niño events.\n")
} else {
  cat("Conclusion: There is no significant difference in the number of fires during El Niño events.\n")
}


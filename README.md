# Clinical Trial Data Analysis


## Overview
This repository contains R code for analyzing and visualizing clinical trial data to evaluate the effectiveness of different treatments. The analysis explores treatment outcomes, adverse events, demographic patterns, and treatment responses across different patient groups.


## Setup & Data Preparation
### Loading Required Packages

```r
library(tidyverse)
```

### Creating the Dataset

```r
clinical_data <- data.frame(
  patient_id = 1:16,
  age = c(34,45,29,51,42,37,48,26,53,39,32,44,55,30,49,38),
  gender = c("Male", "Female", "Female", "Male", "Male",
             "Female", "Male", "Female", "Male", "Female",
             "Male", "Female", "Male", "Female", "Male", "Female"),
  treatment_group = c("Treatment A", "Control", "Treatment B", "Treatment A", "Control",
                      "Treatment B", "Control", "Treatment A", "Treatment B", "Control",
                      "Treatment A", "Treatment B", "Control", "Treatment A", "Treatment B", "Control"),
  baseline_score = c(25, 30, 22, 28, 35,
                     27, 33, 21, 29, 32,
                     26, 24, 31, 23, 36, 20),
  followup_score = c(15, 28, 18, 20, 33,
                     22, 31, 19, 25, 30,
                     24, 20, 29, 22, 34, 19),
  adverse_events = c(1, 0, 2, 3, 0,
                     1, 2, 0, 2, 1,
                     1, 0, 2, 1, 3, 0)
)

# display the dataset
print(clinical_data)
```


## Dataset Description
The dataset includes information from 16 patients participating in a clinical trial, with the following variables:
- patient_id: Unique identifier for each patient
- age: Patient age in years
- gender: Patient gender (Male/Female)
- treatment_group: Treatment assignment (Control, Treatment A, Treatment B)
- baseline_score: Clinical score before treatment
- followup_score: Clinical score after treatment
- adverse_events: Number of reported adverse events


## Dependencies
- R (>= 4.0.0)
- tidyverse


## Analysis Components
### 1. Treatment Effectiveness Analysis
- Calculated mean follow-up scores for each treatment group
- Created bar plots to visualize treatment outcomes
- Used aggregate() and geom_bar() for statistical analysis and visualization

### 2. Adverse Events Analysis
- Examined the distribution of adverse events across treatment groups
- Generated summary statistics including mean, median, and standard deviation
- Visualized patterns using boxplots with geom_boxplot()

### 3. Age Distribution Analysis
- Analyzed demographic patterns in the patient population
- Created histograms to visualize age distribution
- Used geom_histogram() with customized binwidth for clear visualization

### 4. Gender-based Treatment Response
- Investigated treatment effectiveness by gender
- Calculated score changes from baseline to follow-up
- Created scatter plots with geom_point() and facet_wrap() for comparison

### 5. Baseline Score Impact Analysis
- Evaluated the relationship between baseline scores and treatment outcomes
- Created a new variable for score changes
- Visualized relationships using scatter plots


## Key Findings
1. Treatment groups A and B have lower average follow-up scores than the Control group, suggesting treatment effectiveness. Treatment A outperforms Treatment B.
2. Treatment groups A and B show higher adverse events compared to the Control, indicating potential side effects. Treatment B has a higher median of adverse events than Treatment A.
3. The age distribution is evenly spread across the 26-55 range. There is clustering in the 30s and 40s, providing a balanced demographic overview.
4. Gender differences exist in treatment responses. In treatment A, Male show greater improvement, while in treatment B, Female show greater improvement.
5. Baseline scores show negative correlation with treatment outcomes.


## Contributing
Feel free to fork this repository and submit pull requests with improvements or additional analyses.


## License

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

**Note about data usage**: The clinical trial dataset used in this analysis is synthetic and created for educational purposes only.

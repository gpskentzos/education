# Educational Inequality Study

## Project Description

This project addresses inequality of educational opportunity in U.S. high schools. Here we will focus on average student performance on the ACT or SAT exams that students take as part of the college application process.
## Project Overview

This project addresses inequality of educational opportunity in U.S. high schools. Here we will focus on average student performance on the ACT or SAT exams that students take as part of the college application process.

We expect a range of school performance on these exams, but is school performance associated with socioeconomic factors?

This is a broad question that we will make more precise as we consider how we want to answer the question and what data are available. Additionally, each of you will personalize the question by adding a data set to the data I will provide you with.

- **Objective:** Focus on average student performance on the ACT or SAT exams that students take as part of the college application process and determing whether there is a socioeconomic tie.
- **Domain:** Education, Economics, Politics
- **Key Techniques:** Summary statistical and visualization analysis and potentially hypothesis testing and inferences.

---

## Project Structure

```
├── data/                 # Raw data
├── data/processed        # processed data (clean data set)
├── code/                 # Jupyter notebooks and Python scripts
├── reports/              # Generated reports and visualizations
├── requirements.txt      # Python Dependencies
├── README.md             # Project introduction
└── ETHICS.md             # Data science ethics checklist
```

---

## Data

- Cleaned data file: `clean_education_dataset.csv`

- **Source:** https://www.edgap.org/#4/37.71/-95.99
- **Description:** data set from 2016 includes information about average ACT or SAT scores for schools and several socioeconomic characteristics of the school district
- **License:** NA


- **Source:** https://nces.ed.gov/ccd/pubschuniv.asp
- **Description:** This data set consists of basic identifying information about schools
- **License:** NA

- **Source:** https://www2.census.gov/geo/pdfs/maps-data/maps/reference/us_regdiv.pdf?utm_source=chatgpt.com
- https://www.census.gov/library/reference/code-lists/ansi.html#state
- **Description:** Maps each U.S. state and D.C. to its Census region and Census division, with state postal abbreviations and FIPS codes. Used to group schools and summarize ACT results by geographic region. This lookup table is derived from the official Census region/division definitions and ANSI/FIPS state codes. No data values were modified beyond formatting into a simple CSV structure for analysis.
- **License:** NA

- **Source:** https://nces.ed.gov/programs/digest/d17/tables/dt17_226.60.asp
- **Description:** Provides average ACT composite scores and percent of graduates tested by state for the class of 2016. Used to add context to regional analysis—recognizing that ACT participation rates differ widely by state (which influences average scores). Values for 2016 (composite and participation) were extracted directly from the NCES table and combined with the Census region/division data for consistency in analysis.
- **License:** NA
---

## Data Analysis

### Analysis Overview
This project performs a comprehensive analysis of the relationship between socioeconomic factors and ACT performance using linear regression modeling. The analysis includes:

1. **Data Preparation**: Loading, cleaning, and merging four school based datasets 
2. **Feature Engineering**: Creating derived variables including log transformations, interaction terms, and z-scores
3. **Exploratory Analysis**: Correlation analysis, distribution plots, and regional comparisons
4. **Statistical Modeling**: 
   - School-level regression with 6 predictors
   - State-level regression with cross-validation
   - ANOVA testing for regional differences

### Key Findings
- Strong negative association between poverty (FRL%) and ACT scores
- Income and parental education show positive associations with performance
- State ACT participation rate confirms selection bias hypothesis
- Significant regional differences detected

### Files
- **Analysis Notebook**: `code/Education_Analysis_FINAL.ipynb`
- **Clean Dataset**: `data/processed/clean_education_dataset.csv`
- **Outputs**: All figures and tables saved to `reports/` directory

### Reproducibility
Run all cells in order (Restart & Run All) to reproduce all results. The notebook uses relative paths and creates output directories automatically.

---

## Authors

- Paul Skentzos - [@gpskentzos](https://github.com/gpskentzos)

---

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

---

## Acknowledgements

### Data sets:
  https://www.edgap.org/#5/37.875/-96.987
  https://nces.ed.gov/ccd/pubschuniv.asp
  https://www2.census.gov/geo/pdfs/maps-data/maps/reference/us_regdiv.pdf
  https://nces.ed.gov/programs/digest/d17/tables/dt17_226.60.asp

### References:
- James, G., Witten, D., Hastie, T., & Tibshirani, R. (2013). *An Introduction to Statistical Learning*. Springer. Retrieved from https://www.statlearning.com/ (Chapters 3 & 7: Multiple regression and cross-validation)
### Implementation Resources
- Pandas Documentation: Data merging and joining strategies. https://pandas.pydata.org/docs/user_guide/merging.html
- Seaborn Statistical Visualization. https://seaborn.pydata.org/tutorial/regression.html (Regression plots and statistical graphics)
- Scikit-learn: Linear Models. https://scikit-learn.org/stable/modules/linear_model.html (Regression implementation)
### Data Sources
- EdGap.org: School-level socioeconomic and performance data. https://www.edgap.org/
- National Center for Education Statistics (NCES): Common Core of Data and ACT participation statistics. https://nces.ed.gov/
- U.S. Census Bureau: Geographic divisions and state FIPS codes. https://www.census.gov/
### Collaboration
- Stack Overflow community for troubleshooting pandas merge strategies
- Seattle University DATA 5100 course materials and instruction

This analysis builds on established research in educational inequality and applies modern statistical methods to understand the relationship between socioeconomic factors and academic achievement. Statistical techniques including ANOVA, VIF analysis, and cross-validation were implemented following best practices from the data science community.
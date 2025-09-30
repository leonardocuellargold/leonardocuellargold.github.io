---
title: "WV Education Outcomes Modeling"
subtitle: "County-level education prediction using demographic and finance data"
date: 2024-10-05
stack: [R, tidyverse, ggplot2]
featured_image: /assets/img/projects/wv-education-hero.jpg
gallery:
  - src: /assets/img/projects/wv-education-1.jpg
    alt: "Data visualization dashboard"
    caption: "Interactive county-level education metrics"
  - src: /assets/img/projects/wv-education-2.jpg
    alt: "Predictive model results"
    caption: "Model performance and accuracy metrics"
  - src: /assets/img/projects/wv-education-3.jpg
    alt: "Geographic visualization"
    caption: "County-level heatmap of education outcomes"
---

## Project Overview

A comprehensive data analysis project that builds predictive models for West Virginia education outcomes using demographic, economic, and financial data at the county level.

## Research Questions

- What demographic and economic factors most strongly predict education outcomes?
- How do funding levels correlate with student performance across counties?
- Can we identify at-risk counties for targeted intervention?

## Data Sources

- West Virginia Department of Education assessment data
- US Census demographic information
- County-level financial and budget data
- Economic indicators and employment statistics

## Methodology

### Data Collection & Cleaning
- Compiled multi-year datasets from various state and federal sources
- Standardized county identifiers and handled missing data
- Created composite metrics for education outcomes

### Exploratory Analysis
- Correlation analysis between predictors and outcomes
- Geographic visualization of education performance
- Time-series analysis of trends

### Predictive Modeling
- Multiple regression models with cross-validation
- Random forest for feature importance
- Model comparison and validation

## Key Findings

The analysis revealed that socioeconomic factors, particularly poverty rates and parental education levels, were stronger predictors of education outcomes than per-pupil spending alone. Rural counties showed distinct patterns requiring targeted approaches.

## Visualizations

Interactive dashboards built with ggplot2 and R Shiny provide county-level insights for policymakers and educators to identify areas needing support.

## Impact

The findings inform resource allocation decisions and help identify counties that would benefit most from targeted education interventions.
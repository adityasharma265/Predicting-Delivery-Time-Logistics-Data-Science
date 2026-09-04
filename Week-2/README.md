# Week 2: Data Collection, Cleaning and Preprocessing

## Project Title

**Predicting Delivery Time and Improving Logistics Efficiency Using Data Science and Python**

## Overview

Week 2 focuses on preparing a real logistics dataset for further exploratory analysis and predictive modeling. The objective of this stage is to assess data quality, identify potential data issues, clean incorrectly formatted variables and create useful features related to delivery performance.

The dataset used for this stage contains **25,000 delivery records and 15 original variables**.

## Data Quality Assessment

### Missing Values

The dataset contained **0 missing values**. Therefore, no missing-value imputation was required.

### Duplicate Records

The analysis identified **0 completely duplicated rows**. No records were removed through duplicate-row elimination.

### Repeated Delivery IDs

The `delivery_id` variable contained **498 repeated identifier occurrences**. These records were not automatically removed because repeated identifiers do not necessarily indicate that the complete records are duplicates.

## Incorrect Data Types

The following variables were initially stored in an incorrect datetime-like format:

- `delivery_time_hours`
- `expected_time_hours`

These variables were converted into numerical values representing hours so that they could be used for statistical analysis, visualization and machine-learning modeling.

## Feature Engineering

Two additional delivery-performance features were created.

### Delivery Time Difference

`delivery_time_difference_hours = delivery_time_hours - expected_time_hours`

This feature measures the difference between actual and expected delivery time.

### Delivery Delay Flag

A binary variable named `delivery_delay_flag` was created:

- `0` = Delivery completed on time or earlier than expected.
- `1` = Actual delivery time exceeded expected delivery time.

## Outlier Analysis

Potential outliers were evaluated using the Interquartile Range (IQR) method.

The analysis identified:

- Distance: 0 potential outliers
- Package Weight: 0 potential outliers
- Delivery Time: 203 potential outliers
- Expected Delivery Time: 0 potential outliers
- Delivery Rating: 0 potential outliers
- Delivery Cost: 0 potential outliers

The potential delivery-time outliers were retained because unusually long delivery times may represent genuine logistics delays rather than data-entry errors.

## Tools Used

The preprocessing workflow was implemented using:

- Python
- pandas
- NumPy

## Preprocessing Workflow

```text
Load Dataset
      ↓
Inspect Dataset Structure
      ↓
Check Missing Values
      ↓
Check Duplicate Records
      ↓
Investigate Repeated Delivery IDs
      ↓
Correct Data Types
      ↓
Standardize Text Variables
      ↓
Validate Numerical Variables
      ↓
Detect Potential Outliers
      ↓
Feature Engineering
      ↓
Generate Clean Dataset

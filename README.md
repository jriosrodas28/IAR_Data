# Investment Adviser Public Disclosure (IAPD) Data Visualization

## Overview

This project involves visualizing data from the Investment Adviser Public Disclosure (IAPD) system, which provides public access to information about registered investment advisers (IAs) and their representatives (IARs). The dataset used contains detailed records on IARs, including personal information, employment history, licensing details, and customer complaints.

The goal of this project is to explore and visualize various patterns and trends within the data by creating a series of informative charts. The dataset allows us to create a variety of charts, such as:

- **Distribution of a single categorical variable**
- **Distribution of a single quantitative variable**
- **Distribution of two categorical variables**
- **Distribution of a quantitative variable across categories of a categorical variable**
- **Relationship between two quantitative variables**

Additionally, the project explores more complex visualizations like interactive geographic maps.

---

# IAPD Overview

The Investment Adviser Public Disclosure (IAPD) system is a platform managed by the U.S. Securities and Exchange Commission (SEC) and the North American Securities Administrators Association (NASAA). Its primary goal is to enhance transparency by providing public access to information about registered investment advisers and their representatives.

### Representative Compilation Reports

The system generates detailed reports for each individual IAR, which include the following categories:

#### Personal & Registration Information
- Representative's full legal name
- Registration status, jurisdictions, and employer details
- Unique Central Registration Depository (CRD) number

#### Qualifications & Education
- Licenses and certifications 
- Educational background and years of industry experience

#### Disciplinary History
- Details on criminal or regulatory actions, civil lawsuits, bankruptcies, and outcomes

#### Employment History
- Previous employers, job titles, and responsibilities

#### Other Affiliations
- Other business activities, affiliations, and potential conflicts of interest

#### Customer Complaints
- Client complaints, arbitration results, and regulatory investigations

#### Additional Disclosures
- Relevant financial disclosures and other business relationships

---

# Data Preparation: First Stage Summary

The dataset comprises 20 XML files from the SEC’s IAPD system. I used Python to parse and extract key categories of information, such as:

- Personal details
- Employment history
- Registration history
- Licensing exams and certifications
- Disclosures and other business activities

This data was then organized into **pandas DataFrames**, with each DataFrame representing a specific aspect of an IAR’s professional profile.

---

# Data Preparation: Second Stage Summary

In the second stage, I employed an R script to clean and standardize employer names in the dataset. Key steps included:

1. **Standardizing company names**:
   - Converted names to lowercase
   - Removed punctuation and filler words (e.g., "LLC," "Inc," "Group")

2. **Tokenizing company names**:
   - Split company names into individual words and grouped similar names

3. **Mapping company names**:
   - Used a lookup table to assign standardized labels to similar company names

4. **Manual standardization**:
   - Applied case-specific rules (e.g., mapping "morgan stanley" to "Morgan Stanley")

5. **Hashing the CRD number**:
   - The unique CRD number for each representative was **hashed** to obfuscate sensitive data while maintaining the ability to link records in a non-identifiable manner.

Additionally, I added key fields such as:
- Average registration duration
- Average Employment duration
- Employment state and U.S. region

---

# Data Exploration: Summary

The dataset was explored through both static and interactive visualizations, focusing on trends and patterns within the data. Key analyses included:

### 1. **Top 10 Most Common Firms**
   A bar chart displaying the top 10 most common firms.

### 2. **Average Registration Duration**
   A histogram and boxplot showing how long IARs typically remain registered with each registration.

### 3. **Regional Patterns**
   Regional trends were analyzed by visualizing the top 3 firms by employment region and registration volume across U.S. states.

### 4. **Firm Comparison**
   A scatter plot showing the relationship between registration count and average registration duration across firms.

### 5. **Interactive Map**
   Using Plotly, an interactive map was created to visualize firm-level metrics such as total representatives, registrations, and city reach across U.S. states. Users can zoom in to explore specific regions.

---

# What to Expect

The project includes several visualizations that analyze and highlight key insights from the IAPD dataset. Each visualization is followed by a short explanation of the trends or patterns it reveals.

The main visualizations include:

- Static charts: Bar charts, histograms, boxplots, and scatter plots
- Interactive charts: Plotly-powered geographic maps

---

# Note

This README was created with the assistance of a **language model** (LM) to help ensure clarity and readability.

---



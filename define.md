# Data Understanding Phase

The **Data Understanding** phase involves acquiring the initial datasets and examining their properties to identify data quality problems, gain early insights, or detect interesting subsets.

-----

## Key Sub-Phases & Examples

### 1\. Collecting Initial Data

This step involves accessing data from available internal and external sources.

  * **Key Tasks:**
      * Identify potential data sources, including transactional data, web logs, survey results, or purchased demographic datasets.
      * Evaluate attribute relevance, potential merge issues, and handling of missing values across sources.
  * **E-Retail Case Study Example:**
      * **Web Logs:** Raw server access logs containing customer navigation details.
      * **Purchase Data:** Transaction records containing order specifics, which must be mapped to web log sessions.
      * **Product & Customer Databases:** Product details mapped to orders, and registration questionnaire responses mapped to customer IDs.

### 2\. Describing Data

This step focuses on evaluating the quantity, formats, and structure of the collected data.

  * **Key Tasks:**
      * Document record and field counts, data formats (numeric, categorical/symbolic, Boolean), and value coding schemes.
      * Ensure key identifiers across multiple datasets use matching coding schemes for future merges.
  * **E-Retail Case Study Example:**
      * **Scope & Volume:** Analysis was limited to \~30,000 registered users, but encompassed millions of web log records.
      * **Value Types:** Primarily symbolic data (timestamps, page URLs, questionnaire responses) with key numeric variables such as items ordered, purchase amounts, and product dimensions.

### 3\. Exploring Data

Data exploration uses summary statistics, charts, and tables to address the technical goals and form hypotheses.

  * **Key Tasks:**
      * Run statistical queries and visualizations to reveal data distributions and relationships.
      * Formulate and refine hypotheses regarding promising fields.
  * **E-Retail Case Study Example:**
      * **Workflow Customization:** Raw web logs could not be meaningfully explored without prior cleaning/transformation, demonstrating CRISP-DM's non-linear flexibility.
      * **Findings:** Exploration of the purchase database revealed customer spend distributions, while product database checks uncovered typographical errors like a `"119-inch"` monitor.

### 4\. Verifying Data Quality

A thorough quality audit identifies missing fields, inconsistencies, and errors prior to modeling.

  * **Key Tasks:**
      * Audit for missing values, typographical errors, measurement errors, and coding inconsistencies.
  * **E-Retail Case Study Example:**
      * **Missing Data:** Unanswered survey items by registered users.
      * **Measurement Errors:** Ambiguous or poorly worded questionnaire items.

-----

# Data Preparation Phase

The **Data Preparation** phase encompasses all activities required to construct the final dataset used for modeling from the raw data. It typically consumes 50% to 70% of a project's time and effort.

-----

## Key Sub-Phases & Examples

### 1\. Selecting Data

This step determines which records and attributes will be included or excluded from the model.

  * **Key Tasks:**
      * Select target records (rows) and attributes (columns) based on relevance to the objectives, quality, and technical constraints.
  * **E-Retail Case Study Example:**
      * **Selecting Items:** Filtered out non-registered site visitors and web log entries referencing image files.
      * **Selecting Attributes:** Excluded sensitive personally identifiable information (PII) such as customer names, physical addresses, phone numbers, and credit card details.

### 2\. Cleaning Data

Cleaning addresses data quality issues identified during the verification audit.

  * **Key Tasks:**
      * Handle missing values by imputing estimated values or dropping records.
      * Correct data errors, resolve coding inconsistencies, and fix metadata errors.
  * **E-Retail Case Study Example:**
      * **Survey Non-Response:** Modeled purchasing differences between survey respondents and non-respondents to check if missing surveys introduced bias.
      * **Flawed Items:** Filtered out poorly worded questionnaire attributes from downstream models.

### 3\. Constructing New Data

This step generates derived fields or new records needed for analysis.

  * **Key Tasks:**
      * Create derived attributes using mathematical or logical transformations.
      * Aggregate or summarize records.
  * **E-Retail Case Study Example:**
      * **Derived Attributes:** Created session timestamps, visitor IDs, and calculated time elapsed between web events.
      * **Aggregated Summaries:** Summarized log events at the session level (total actions, total time spent, total purchases) and at the customer level.

### 4\. Integrating Data

Data integration combines information from multiple datasets.

  * **Key Tasks:**
      * **Merging:** Join datasets with matching records using a primary key.
      * **Appending:** Stack datasets with identical attributes but different records.
  * **E-Retail Case Study Example:**
      * Merged customer and product details into processed web log event records.
      * Merged summarized session and transaction totals directly into the main customer database.

### 5\. Formatting Data

Formatting adjustments prepare the dataset according to the specific syntax or structural requirements of selected algorithms.

  * **Key Tasks:**
      * Reorder or sort data records prior to running specialized model nodes.
  * **E-Retail Case Study Example:**
      * Presorted input datasets using a Sort node to satisfy sequence algorithm prerequisites and optimize execution times.

-----

Would you like me to detail the remaining **Modeling**, **Evaluation**, and **Deployment** phases along with their case study examples?

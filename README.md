# Chapter 1: Introduction to CRISP-DM

The **CRISP-DM** (*Cross-Industry Standard Process for Data Mining*) methodology provides a structured, non-proprietary, and application-neutral lifecycle for data science and analytics initiatives. It structures project workflows into six non-linear, iterative phases where insights gained in later steps frequently inform refinements in earlier stages.

```
               ┌───────────────────────────┐
               │   Business Understanding  │◄─────────┐
               └─────────────┬─────────────┘          │
                             │                        │
                             ▼                        │
               ┌───────────────────────────┐          │
               │    Data Understanding     │          │
               └─────────────┬─────────────┘          │
                             │                        │
                             ▼                        │
               ┌───────────────────────────┐          │
               │     Data Preparation      │◄───────┐ │
               └─────────────┬─────────────┘        │ │
                             │                      │ │
                             ▼                      │ │
               ┌───────────────────────────┐        │ │
               │         Modeling          │────────┘ │
               └─────────────┬─────────────┘          │
                             │                        │
                             ▼                        │
               ┌───────────────────────────┐          │
               │        Evaluation         │──────────┘
               └─────────────┬─────────────┘
                             │
                             ▼
               ┌───────────────────────────┐
               │        Deployment         │
               └───────────────────────────┘

```

---

# Chapter 2: Business Understanding

The **Business Understanding** phase focuses on uncovering organizational expectations, translating business challenges into data problems, evaluating operational feasibility, and establishing a structured project plan before technical execution begins.

```
┌─────────────────────────────────────────────────────────────────────────┐
│                          BUSINESS UNDERSTANDING                         │
├───────────────────┬───────────────────┬────────────────┬────────────────┤
│  1. Business      │  2. Situation     │ 3. Data Mining │ 4. Project     │
│     Objectives    │     Assessment    │    Goals       │    Plan        │
└───────────────────┴───────────────────┴────────────────┴────────────────┘

```

---

### Module 2.1: Determining Business Objectives

This sub-phase establishes foundational business context, defines core goals, and sets quantitative and qualitative measures of commercial success.

#### Key Core Tasks

* **Compile Business Background:** Document organizational structures, internal sponsors, affected operational units, existing solutions, and key problem areas.
* **Define Business Objectives:** Formulate high-level commercial goals and document expected organizational outcomes.
* **Establish Business Success Criteria:** Define concrete Key Performance Indicators (KPIs) and qualitative criteria to evaluate project outcomes.

#### Case Study Application (E-Retailer)

* **Context & Objective:** An established electronics e-retailer faced intense market competition and rising customer acquisition costs. To sustain profitability, the company commissioned a study to cultivate existing relationships by improving cross-sales and driving customer loyalty.
* **Success Criteria:** Achieve a 10% increase in cross-sales, increase customer time and page views per visit, and complete the project on time and within budget.

---

### Module 2.2: Assessing the Situation

This sub-phase conducts an operational audit of resources, technical constraints, organizational assumptions, risk factors, and commercial returns.

#### Key Core Tasks

* **Resource Inventory:** Audit hardware infrastructure, personnel (domain experts, system administrators), and accessible data assets.
* **Requirements, Assumptions, and Constraints:** Verify compliance, regulatory, and legal rules, delivery schedules, budget boundaries, and system access rights.
* **Risks and Contingencies:** Identify technical, financial, or data-related failure points and establish actionable backup plans.
* **Terminology & Cost/Benefit Analysis:** Construct a shared glossary across business and technical teams, and evaluate expected project ROI against development costs.

#### Case Study Application (E-Retailer)

* **Personnel:** The company possessed strong in-house knowledge of server logs and transactional databases, but lacked dedicated data warehousing experience, prompting them to hire an external data mining specialist.
* **Data & Constraints:** Large volumes of web server logs and purchase records were available; the study was restricted exclusively to registered site users.
* **Risks & Contingency:** To mitigate schedule and budget risks, execution was capped at a single fiscal quarter, with a contingency plan to reduce project scope if constraints were threatened.

---

### Module 2.3: Determining Data Mining Goals

This sub-phase translates abstract business objectives into technical data mining tasks and quantitative algorithmic benchmarks.

#### Key Core Tasks

* **Define Technical Objectives:** Map business problems to technical data mining problem types (e.g., classification, regression, clustering, association rules, sequence analysis).
* **Define Data Mining Success Criteria:** Establish technical evaluation benchmarks (e.g., accuracy rates, error margins, lift factors).

#### Case Study Application (E-Retailer)

* **Market Basket Analysis:** Analyze transaction histories to discover associations between complementary products for dynamic recommendations.
* **Customer Profiling:** Segment web access logs to identify intent and dynamically display personalized homepage content.
* **Sequence Analysis:** Predict a user's next site destination based on historical navigation pathways.

---

### Module 2.4: Producing a Project Plan

The final sub-phase generates a master operational plan detailing stage durations, resource assignments, technical dependencies, and decision checkpoints across all process phases.

#### Key Core Tasks

* Estimate phase durations, resource dependencies, and required effort.
* Plan for post-evaluation deployment workflows and identify formal review gates.
* Select appropriate modeling tools, techniques, and software architectures.

#### Case Study Application (Sample Master Plan)

| CRISP-DM Phase | Estimated Duration | Assigned Resources | Primary Risk Factor |
| --- | --- | --- | --- |
| **Business Understanding** | 1 Week | All Analysts | Shifting economic conditions |
| **Data Understanding** | 3 Weeks | All Analysts | System access / technical obstacles |
| **Data Preparation** | 5 Weeks | Consultant, Database Analyst | Data quality / schema defects |
| **Modeling** | 2 Weeks | Consultant, Database Analyst | Sub-optimal model performance |
| **Evaluation** | 1 Week | All Analysts | Inability to operationalize findings |
| **Deployment** | 1 Week | Consultant, Database Analyst | Integration failure into live workflows |

---

# Chapter 3: Data Understanding

The **Data Understanding** phase involves acquiring initial data assets, evaluating structural properties, exploring statistical distributions, and verifying quality to establish a verified base for downstream preprocessing.

```
┌─────────────────────────────────────────────────────────────────────────┐
│                            DATA UNDERSTANDING                           │
├───────────────────┬───────────────────┬────────────────┬────────────────┤
│  1. Initial Data  │  2. Data          │ 3. Data        │ 4. Quality     │
│     Collection    │     Description   │    Exploration │    Verification│
└───────────────────┴───────────────────┴────────────────┴────────────────┘

```

---

### Module 3.1: Collecting Initial Data

This sub-phase accesses and ingests data from internal databases, flat files, APIs, or external providers.

#### Key Core Tasks

* Acquire target datasets (transaction logs, web access files, survey responses, demographics).
* Audit field availability, potential join keys, and integration issues across sources.
* Document acquisition methods and technical hurdles in a Data Collection Report.

#### Case Study Application (E-Retailer)

* **Web Logs:** Extracted raw server access logs containing customer clickstream events.
* **Purchase Data:** Extracted transactional records containing line-item orders to be mapped to user web sessions.
* **Product & Customer Databases:** Integrated product catalog metadata and user questionnaire responses linked via primary customer IDs.

---

### Module 3.2: Describing Data

This sub-phase audits structural attributes, volume, field definitions, and schema formats.

#### Key Core Tasks

* Document record counts, feature counts, data types (numeric, categorical, Boolean, timestamps), and coding schemes.
* Verify identifier fields across datasets to confirm compatibility for future joins.
* Document findings in a Data Description Report (Data Dictionary foundation).

#### Case Study Application (E-Retailer)

* **Scope & Volume:** Analysis was restricted to ~30,000 registered users, covering millions of web log events.
* **Data Types:** Mostly symbolic data (timestamps, page URLs, survey responses) alongside key numeric attributes (item quantities, order totals, product dimensions).

---

### Module 3.3: Exploring Data (EDA)

This sub-phase applies summary statistics, query profiling, and graphical visualization to uncover patterns and refine hypotheses.

#### Key Core Tasks

* Compute summary statistics and plot distributions to examine feature relationships.
* Formulate and test data-driven hypotheses regarding target predictive signals.
* Document initial findings in a Data Exploration Report.

#### Case Study Application (E-Retailer)

* **Workflow Adjustments:** Raw server access logs required preliminary cleaning before meaningful exploration could occur, illustrating the iterative nature of CRISP-DM.
* **Findings:** Transaction profiling revealed customer spending distributions, while catalog audits uncovered data-entry errors (e.g., a `"119-inch"` monitor).

---

### Module 3.4: Verifying Data Quality

This sub-phase performs a formal audit to identify missing values, outliers, errors, and inconsistencies prior to modeling.

#### Key Core Tasks

* Audit datasets for missing entries, incorrect formatting, extreme outliers, and invalid codes.
* Document defects, potential operational impacts, and remediation plans in a Data Quality Report.

#### Case Study Application (E-Retailer)

* **Missing Data:** Unanswered survey questions among registered customer profiles.
* **Measurement Errors:** Identified ambiguous and poorly worded questionnaire items that generated unreliable response patterns.

---

# Chapter 4: Data Preparation

The **Data Preparation** phase covers all activities required to transform raw sources into a clean, feature-engineered matrix for modeling, often consuming 50% to 70% of total project effort.

```
┌───────────────────────────────────────────────────────────────────────────────────┐
│                                 DATA PREPARATION                                  │
├───────────────┬───────────────┬───────────────────┬───────────────┬───────────────┤
│ 1. Data       │ 2. Data       │ 3. Constructing   │ 4. Data       │ 5. Data       │
│    Selection  │    Cleaning   │    New Data       │    Integration│    Formatting │
└───────────────┴───────────────┴───────────────────┴───────────────┴───────────────┘

```

---

### Module 4.1: Selecting Data

This sub-phase determines which subsets of records (rows) and attributes (columns) will be retained or excluded from modeling.

#### Key Core Tasks

* Select candidate predictor features and target variables based on quality, relevance, and business goals.
* Filter out irrelevant records, non-target populations, or noisy observations.
* Document selection rationale, including data leakage and regulatory considerations.

#### Case Study Application (E-Retailer)

* **Record Selection:** Excluded unregistered visitor logs and web access requests for static image files (`.gif`, `.jpg`).
* **Attribute Selection:** Dropped personally identifiable information (PII) including customer names, street addresses, telephone numbers, and credit card credentials.

---

### Module 4.2: Cleaning Data

This sub-phase remediates dirty data by executing imputation, filtering, or correction routines.

#### Key Core Tasks

* Impute missing values or delete incomplete records using statistically sound strategies.
* Standardize dirty text entries, cap or transform extreme outliers, and resolve data anomalies.
* Document all preprocessing routines in a Data Cleaning Report.

#### Case Study Application (E-Retailer)

* **Survey Bias Check:** Modeled purchasing behavior differences between survey respondents and non-respondents to ensure non-response did not introduce bias.
* **Attribute Removal:** Filtered out poorly worded questionnaire attributes from downstream datasets.

---

### Module 4.3: Constructing New Data (Feature Engineering)

This sub-phase generates derived attributes, aggregated indicators, or transformed variables to enhance predictive signals.

#### Key Core Tasks

* Derive new metrics using mathematical, logical, or temporal transformations.
* Aggregate low-granularity events into high-level summary records.

#### Case Study Application (E-Retailer)

* **Derived Attributes:** Calculated session timestamps, unique visitor IDs, and elapsed duration between clickstream events.
* **Aggregations:** Summarized event-level logs into session summaries (total actions, total duration, checkout status) and customer-level metrics.

---

### Module 4.4: Integrating Data

This sub-phase merges disparate datasets, tables, or summary metrics into a single analytical view.

#### Key Core Tasks

* Combine datasets using SQL-style join operations on matching primary keys.
* Union or append datasets sharing identical schemas across different time periods.

#### Case Study Application (E-Retailer)

* Joined customer profiles and product metadata onto processed web log event records.
* Merged aggregated session and transactional totals directly into the master customer database.

---

### Module 4.5: Formatting Data

This sub-phase restructures dataset syntax, column ordering, or encoding to meet algorithm requirements.

#### Key Core Tasks

* Perform categorical encoding (e.g., One-Hot, Ordinal Encoding) and numerical feature scaling.
* Reorder, sort, or rename attributes to meet model interface expectations.

#### Case Study Application (E-Retailer)

* Pre-sorted input tables using a Sort node to satisfy sequence algorithm prerequisites and optimize execution times.

---

# Chapter 5: Modeling

The **Modeling** phase selects, builds, tunes, and evaluates algorithms to extract actionable patterns from prepared datasets.

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                MODELING                                 │
├───────────────────┬───────────────────┬────────────────┬────────────────┤
│  1. Technique     │  2. Test          │ 3. Model       │ 4. Model       │
│     Selection     │     Design        │    Building    │    Assessment  │
└───────────────────┴───────────────────┴────────────────┴────────────────┘

```

---

### Module 5.1: Selecting Modeling Techniques

This sub-phase selects candidate algorithms aligned with the technical task, target data types, and operational requirements.

#### Key Core Tasks

* Choose primary algorithms and baseline benchmarks based on problem type.
* Document underlying mathematical assumptions (e.g., linearity, feature independence, missing value sensitivity).

#### Case Study Application (E-Retailer)

* **Recommendations:** Selected TwoStep and Kohonen network clustering algorithms to segment customer purchases, followed by C5.0 decision tree rule induction to profile generated clusters.
* **Navigation Profiling:** Applied a Sequence modeling algorithm to web access logs to discover browsing paths.

---

### Module 5.2: Generating a Test Design

This sub-phase designs a validation framework to evaluate model performance and generalization.

#### Key Core Tasks

* Define technical metrics for success (e.g., error rates, precision, recall, lift, interpretability).
* Split datasets into training, validation, and test subsets (or set up cross-validation).

#### Case Study Application (E-Retailer)

* **Recommendations:** Defined subjective business criteria—rules had to be simple enough to be actionable while complex enough to enable personalization.
* **Navigation Profiling:** Defined objective technical metrics based on ease of accessing key catalog pages.

---

### Module 5.3: Building & Running Models

This sub-phase executes algorithms on training data and optimizes performance via hyperparameter tuning.

#### Key Core Tasks

* Train candidate models using default hyperparameter configurations.
* Fine-tune hyperparameters to optimize validation metrics while preventing overfitting.
* Document parameter choices, execution runtimes, and resource demands.

#### Case Study Application (E-Retailer)

* **Recommendations:** Generated clusterings across different levels of data integration using varied parameter settings for TwoStep and Kohonen networks.
* **Navigation Profiling:** Executed the Sequence algorithm across varying minimum support thresholds to filter out rare paths and isolate primary navigation trends.

---

### Module 5.4: Assessing the Model

This sub-phase evaluates candidate models technically, ranks performance, and verifies execution against design goals.

#### Key Core Tasks

* Evaluate outputs using evaluation charts, gains/lift charts, or confusion matrices.
* Rank candidate models based on performance, speed, interpretability, and business logic.
* Re-evaluate hyperparameter settings or flag necessary upstream revisions.

#### Case Study Application (E-Retailer)

* **Recommendations:** Both TwoStep and Kohonen models produced strong results; business rules were established to resolve discrepancies between them.
* **Navigation Profiling:** The Sequence model accurately identified common browsing pathways, establishing clear priorities for site layout updates.

---

# Chapter 6: Evaluation

The **Evaluation** phase evaluates constructed models against the overarching business objectives established in Phase 1 before committing to deployment.

```
┌─────────────────────────────────────────────────────────────────────────┐
│                               EVALUATION                                │
├───────────────────────────┬───────────────────────────┬─────────────────┤
│  1. Evaluate Results      │  2. Review Process        │ 3. Next Steps   │
└───────────────────────────┴───────────────────────────┴─────────────────┘

```

---

### Module 6.1: Evaluating Results

This sub-phase translates technical metrics into commercial business impact to confirm goal alignment.

#### Key Core Tasks

* Compare technical findings directly against business success criteria.
* Evaluate models against real-world operational scenarios and audit for unintended biases or risks.
* Approve the final model candidate for deployment.

#### Case Study Application (E-Retailer)

* **Outcome Verification:** Confirmed that navigation sequence models provided clear guidance for site redesigns and recommendation engines.
* **New Insights:** Identified that missing profile data limited recommendation precision, raising new strategic questions regarding profile collection methods.

---

### Module 6.2: Reviewing the Process

This sub-phase audits the end-to-end execution of all CRISP-DM phases to identify mistakes, efficiency bottlenecks, or data leaks.

#### Key Core Tasks

* Review activities, decisions, and transformations executed across all six phases.
* Identify process bottlenecks, unexpected findings, or execution dead ends.

#### Case Study Application (E-Retailer)

* **Process Takeaway:** The organization recognized that backtracking between phases is a natural strength of the iterative framework.
* **Lessons Learned:** Log preparation requires significant time, and maintaining focus on business goals prevents aimless model construction.

---

### Module 6.3: Determining Next Steps

This sub-phase decides whether to proceed to deployment, iterate back to earlier phases, or pause execution.

#### Key Core Tasks

* Decide whether to deploy, adjust hyperparameter ranges, alter feature engineering routines, or re-frame business targets.

#### Case Study Application (E-Retailer)

* **Decision:** Confirmed sufficient model performance and business alignment to proceed directly to operational deployment.

---

# Chapter 7: Deployment

The **Deployment** phase translates analytical models into operational tools, live scoring systems, executive dashboards, or business processes.

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                DEPLOYMENT                               │
├───────────────────┬───────────────────┬────────────────┬────────────────┤
│  1. Deployment    │  2. Monitoring &  │ 3. Final       │ 4. Final       │
│     Planning      │     Maintenance   │    Reporting   │    Review      │
└───────────────────┴───────────────────┴────────────────┴────────────────┘

```

---

### Module 7.1: Planning for Deployment

This sub-phase designs a step-by-step strategy for integrating model deliverables into live enterprise systems.

#### Key Core Tasks

* Define technical deployment architectures (e.g., batch scoring, real-time REST APIs, embedded logic).
* Train end-users and notify affected engineering, infrastructure, and business teams.

#### Case Study Application (E-Retailer)

* **Executive Decision Makers:** Received high-level executive summaries detailing proposed website layout updates.
* **Developers & DBAs:** Received technical specifications for site navigation redesigns and database attribute requirements.

---

### Module 7.2: Planning Monitoring and Maintenance

This sub-phase establishes tracking systems to monitor performance decay, concept drift, and data shifts over time.

#### Key Core Tasks

* Define operational metrics, performance alert thresholds, and accuracy degradation triggers.
* Establish scheduled or trigger-based retraining workflows.

#### Case Study Application (E-Retailer)

* **Initial Checks:** Tracked cross-sales metrics and verified whether customer navigation routes shortened post-deployment.
* **Automation Strategy:** Automated recommendation rule updates for new registered accounts, while setting up periodic manual reviews for cluster updates.

---

### Module 7.3: Producing Final Reports

This sub-phase packages technical documentation, code artifacts, and executive summaries for organizational handover.

#### Key Core Tasks

* Draft business-focused executive summaries detailing financial outcomes and operational impacts.
* Compile comprehensive technical documentation covering data pipelines, schemas, code bases, and API specifications.

#### Case Study Application (E-Retailer)

* **Key Finding:** Uncovered that non-purchasing visitors fell into two distinct time-spent clusters, revealing that lengthy visits often indicated user navigation struggles rather than high engagement.

---

### Module 7.4: Conducting a Final Project Review

The final sub-phase evaluates overall project execution, collects stakeholder feedback, and archives project assets.

#### Key Core Tasks

* Conduct post-implementation interviews with stakeholders, team members, and users.
* Document lessons learned and safely archive code, features, data dictionaries, and model weights.

#### Case Study Application (E-Retailer)

* **Internal Feedback:** Team members supported future analytics initiatives, while system administrators noted increased database load and recommended dedicated server capacity.
* **Customer Feedback:** New users responded positively to layout changes, whereas established registered users required targeted communication to adapt to updated navigation flows.

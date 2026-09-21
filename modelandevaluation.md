Modeling PhaseThe **Modeling** phase involves selecting and applying various modeling techniques, fine-tuning their parameters, and running them iteratively to address the data mining goals.

-----

### Key Sub-Phases & Examples

#### 1\. Selecting Modeling Techniques

This sub-phase focuses on determining the most appropriate algorithms based on available data types, business goals, and specific model requirements.

  * **Key Tasks:**
      * Choose algorithms suitable for the target data types (e.g., categorical vs. continuous).
      * Select techniques aligned with project goals (e.g., clustering vs. rule generation vs. sequence analysis).
  * **E-Retail Case Study Example:**
      * **Recommendations:** Selected TwoStep and Kohonen network clustering algorithms to segment purchases, followed by C5.0 rule induction to profile clusters.
      * **Site Navigation:** Applied a Sequence modeling algorithm to Web logs to discover unique browsing paths.

#### 2\. Generating a Test Design

Before building the models, a plan is created to evaluate their accuracy and validity.

  * **Key Tasks:**
      * Define criteria for model "goodness" (e.g., error rates for supervised models; interpretability or speed for unsupervised models).
      * Partition data into training and testing sets where applicable.
  * **E-Retail Case Study Example:**
      * **Recommendations:** Established subjective business criteria—rules had to be simple enough to make business sense yet complex enough to provide personalized recommendations.
      * **Site Navigation:** Defined objective criteria based on ease of accessing key pages.

#### 3\. Building & Running Models

This step involves executing the algorithms on prepared datasets and experimenting with parameter settings.

  * **Key Tasks:**
      * Run initial models using default parameter settings.
      * Adjust parameters (e.g., tree depth, minimum support thresholds) to optimize results.
      * Document settings, processing speeds, and execution issues.
  * **E-Retail Case Study Example:**
      * **Recommendations:** Generated clusterings across different levels of data integration using varied parameter settings for TwoStep and Kohonen networks.
      * **Site Navigation:** Used the Sequence node with varying minimum support criteria to filter out rare paths and focus on common navigation trends.

#### 4\. Assessing the Model

Models are formally evaluated and ranked according to technical precision and business logic.

  * **Key Tasks:**
      * Analyze model output using analysis nodes, evaluation charts, or lift/gains charts.
      * Rank models based on objective accuracy and subjective ease of interpretation.
  * **E-Retail Case Study Example:**
      * **Recommendations:** Both TwoStep and Kohonen models produced solid results; business rules were developed to resolve discrepancies between them.
      * **Site Navigation:** The Sequence model accurately predicted common customer paths, outlining clear and manageable site layout adjustments.

-----

Evaluation PhaseThe **Evaluation** phase ensures that the technical models meet the broader business goals established at the beginning of the project.

-----

### Key Sub-Phases & Examples

#### 1\. Evaluating the Results

This step formalizes the assessment of whether findings address organizational objectives.

  * **Key Tasks:**
      * Compare model findings directly against original business success criteria.
      * Compile a final list of approved models for deployment.
  * **E-Retail Case Study Example:**
      * **Outcome:** Confirmed that browsing sequences provided clear guidance for site redesign and product recommendation rulesets.
      * **New Insights:** Highlighted that missing customer data limited recommendation precision, prompting new questions about how to gather more customer profiles.

#### 2\. Reviewing the Process

The team reflects on the execution of each phase to identify mistakes, dead ends, or improvements for future projects.

  * **Key Tasks:**
      * Summarize activities and decisions across all CRISP-DM phases.
      * Identify potential bottlenecks, unexpected findings, or alternative approaches.
  * **E-Retail Case Study Example:**
      * **Takeaway:** The e-retailer recognized that backtracking between phases is a strength of the cyclic process.
      * **Lessons Learned:** Log preparation requires significant time, and maintaining focus on business goals prevents aimless model construction.

#### 3\. Determining Next Steps

A strategic decision is made to either proceed with deployment or perform another iteration of modeling.

  * **Key Tasks:**
      * Decide whether to move forward, refine parameters, or adjust project scope.
  * **E-Retail Case Study Example:**
      * **Decision:** Confirmed sufficient model accuracy and relevance to proceed directly to the deployment phase.

-----

Deployment PhaseThe **Deployment** phase translates model insights into operational changes, reports, or automated business systems.

-----

### Key Sub-Phases & Examples

#### 1\. Planning for Deployment

A step-by-step plan is created to integrate model outputs into business workflows.

  * **Key Tasks:**
      * Create integration plans for technical deliverables (e.g., scoring pipelines) and communication plans for executive findings.
      * Notify affected departments and technical administrators.
  * **E-Retail Case Study Example:**
      * **Decision Makers:** Received high-level summaries explaining proposed site changes.
      * **Web Developers & DBAs:** Briefed on site layout updates and new database attribute requirements.

#### 2\. Planning Monitoring & Maintenance

This sub-phase defines mechanisms to monitor live performance and recognize when models become obsolete.

  * **Key Tasks:**
      * Define tracking metrics, accuracy thresholds, and expiration triggers.
      * Outline procedures for retraining models with new data.
  * **E-Retail Case Study Example:**
      * **Initial Checks:** Monitored whether cross-sales increased and user navigation routes shortened after deployment.
      * **Automation:** Automated rule applications for new registered users while scheduling periodic manual reviews for cluster updates.

#### 3\. Producing Final Reports & Presentations

Findings are packaged and communicated to target audiences.

  * **Key Tasks:**
      * Write technical and business-focused documentation outlining problems, costs, results, and deployment strategies.
  * **E-Retail Case Study Example:**
      * **Key Finding:** Uncovered that non-purchasing visitors fell into two distinct time-spent clusters, revealing that lengthy visits often indicated user navigation struggles rather than high engagement.

#### 4\. Conducting a Final Project Review

The final wrap-up phase evaluates overall project performance and collects lessons learned.

  * **Key Tasks:**
      * Interview key stakeholders, project team members, and affected customers.
      * Synthesize feedback into a final project post-mortem.
  * **E-Retail Case Study Example:**
      * **Internal Feedback:** Team members supported future projects, while DBAs noted increased system load and recommended dedicated staffing.
      * **Customer Feedback:** New users responded positively to layout changes, whereas established registered users needed careful communication to adapt to new navigation paths.

-----

Would you like to explore any specific algorithm implementations or data transformation techniques in IBM SPSS Modeler?

---
title: "Blog 3"
date: 2026-08-11
weight: 4
chapter: false
pre: " <b> 3.4. </b> "
---
# TRACKING MACHINE LEARNING EXPERIMENTS WITH AMAZON SAGEMAKER EXPERIMENTS

While building a sales forecasting project on AWS, I realized that training the model is only a small part of the job. The more time-consuming and easily overlooked part is managing experiments: tracking which parameters were tested, their outcomes, and which run produced the best model. 

Amazon SageMaker Experiments is the service I utilized to solve this issue. Interestingly, the entire tracking process can be seamlessly integrated into a local Python script using `boto3`, without the strict requirement of training the model on SageMaker infrastructure.

### 1. Context: The Problem of Manual Experiment Tracking
When the number of experiment runs exceeds a few dozen, manually logging results into a CSV file reveals several weaknesses:
* Difficulties in multi-dimensional comparison (evaluating RMSE, MAPE, training time, and feature count simultaneously).
* Requires manual effort to maintain file structures and write visualization code.
* Highly prone to human errors (incorrect or missing entries).
* Extremely difficult to share synchronized results and charts with other team members.

### 2. What is Amazon SageMaker Experiments?
SageMaker Experiments is a dedicated service designed to organize, track, and compare Machine Learning runs.
* **Hierarchical Structure:** It consists of an Experiment (the overarching project), Run (each specific iteration), and Metric (logged indicators).
* **Visual Interface:** Integrated directly into the AWS Console, allowing users to select comparison columns, filter conditions, and render charts without writing a single line of code.

### 3. Integration with Local Training Scripts
To integrate SageMaker Experiments locally, you simply invoke the `boto3` API within your Python script:
* **Workflow:** Create an Experiment $\rightarrow$ Create a new Run for each training iteration $\rightarrow$ Log input parameters (learning rate, max depth, etc.) and output metrics (RMSE, MAPE).
* **IAM Configuration:** Ensure that the local AWS credentials (user/role) possess the `sagemaker:CreateExperiment`, `sagemaker:CreateRun`, and `sagemaker:BatchPutMetrics` permissions. Missing any of these will throw an `AccessDeniedException`.

### 4. Comparing Runs on the UI
* **Side-by-side Comparison Table:** Instantly identify the run with the lowest RMSE or evaluate how specific hyperparameters affect overall performance.
* **Metric Charting:** For XGBoost, logging RMSE per boosting round clearly visualizes the learning curve. This makes it incredibly easy to pinpoint overfitting and verify if early stopping is functioning correctly.

### 5. Noteworthy Points
* **Naming Conventions:** Experiment names must be globally unique within the same region and account. It is recommended to use `try/except` to catch `ResourceInUse` errors or append timestamps to ensure uniqueness.
* **Data Retention:** Logged data is not deleted automatically. You must proactively use the API to clean up obsolete Runs and Experiments to keep your dashboard organized.
* **Cost Structure:** Pricing is based on the number of metrics logged. While the cost is generally negligible for small to medium projects, it should be monitored if you log an excessive amount of metrics.

### 6. Conclusion
SageMaker Experiments provides a visually intuitive, centrally stored, and easily shareable tracking system. By simply adding a few `boto3` commands to an existing script, you can completely solve the parameter management problem without having to migrate your entire training infrastructure to the cloud.

**References:**
* AWS Documentation – Amazon SageMaker Experiments: https://docs.aws.amazon.com/sagemaker/latest/dg/experiments.html
* AWS Documentation – SageMaker Python SDK Experiments: https://sagemaker-experiments.readthedocs.io/

[*...\[The post link on AWS Study Group\]...*](https://www.facebook.com/groups/660548818043427/?multi_permalinks=2227796681318625&ref=share)
<walkthrough-tutorial-duration duration="30"></walkthrough-tutorial-duration>
{{ author('Cosmin Pintoiu', 'https://www.linkedin.com/in/cosmin-pintoiu/') }}
<walkthrough-tutorial-difficulty difficulty="3"></walkthrough-tutorial-difficulty>
<bootkon-cloud-shell-note/>

During this lab, you gather user feedback to assess the impact of model adjustments on real-world use (prediction), ensuring that our fraud detection system effectively balances accuracy with user satisfaction. 
* Use Dataform, BigQuery and Gemini to Perform sentiment analysis of customer feedback.
### Dataform 

Dataform is a fully managed service that helps data teams build, version control, and orchestrate SQL workflows in BigQuery. It provides an end-to-end experience for data transformation, including:

* Table definition: Dataform provides a central repository for managing table definitions, column descriptions, and data quality assertions. This makes it easy to keep track of your data schema and ensure that your data is consistent and reliable.  
* Dependency management: Dataform automatically manages the dependencies between your tables, ensuring that they are always processed in the correct order. This simplifies the development and maintenance of complex data pipelines.  
* Orchestration: Dataform orchestrates the execution of your SQL workflows, taking care of all the operational overhead. This frees you up to focus on developing and refining your data pipelines.

Dataform is built on top of Dataform Core, an open source SQL-based language for managing data transformations. Dataform Core provides a variety of features that make it easy to develop and maintain data pipelines, including:

* Incremental updates: Dataform Core can incrementally update your tables, only processing the data that has changed since the last update. 
* Slowly changing dimensions: Dataform Core provides built-in support for slowly changing dimensions, which are a common type of data in data warehouses.   
* Reusable code: Dataform Core allows you to write reusable code in JavaScript, which can be used to implement complex data transformations and workflows.

Dataform is integrated with a variety of other Google Cloud services, including GitHub, GitLab, Cloud Composer, and Workflows. This makes it easy to integrate Dataform with your existing development and orchestration workflows.  

### Use Cases for Dataform

Dataform can be used for a variety of use cases, including:

* Data Warehousing: Dataform can be used to build and maintain data warehouses that are scalable and reliable.  
* Data Engineering: Dataform can be used to develop and maintain data pipelines that transform and load data into data warehouses.  
* Data Analytics: Dataform can be used to develop and maintain data pipelines that prepare data for analysis.  
* Machine Learning: Dataform can be used to develop and maintain data pipelines that prepare data for machine learning models.

***


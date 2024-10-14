# Workshop_DataTH
Welcome to my workshop! In this session, I will share various case studies and practical examples from my learning journey through DataTH, an online platform offering the "Road to Data Engineer" course. The content here showcases the skills and knowledge I’ve gained. This workshop covers the following topics:

Workshop1 :
  - Converting data into a Pandas DataFrame
  - Calling an API
  -  Joining two datasets
  - Viewing data in a database using a Pandas DataFrame
  - Saving data after converting from a database

Workshop2 :
  - Set enviroment variable
  - PySpark Setup
  - Data Profiling
  - Data Exploration
  - Data Visualization with Seaborn and Plotly
  - Data Cleansing with Spark
    Timestamp: Incorrect data types and formats

  - Anomalies Check :
    -  Syntactical Anomalies
       Lexical errors such as misspellings
    -  Semantic Anomalies
       Integrity Constraints: Values outside acceptable ranges
    -  Coverage Anomalies
       Missing Values: Checking and replacing empty values
    -  Outliers: Data significantly higher or lower than the majority
    -  Clean Data with Spark SQL
    -  Save Data to CSV

Workshop 3:

  - Comparison between Cloud and On-Premise
  - Introduction to various Cloud concepts, such as Managed Services and Serverless computing
  - Getting to know different services on Google Cloud
  - Comparison of Data Processing and Storage
  - Learning the basics of Command-line (Bash)
    - In this coding session, we will work with both Cloud Shell and Cloud Storage for uploading and downloading files through coding.

Workshop 4:
  - Understanding the tools used for creating Data Pipelines
  - Introduction to the concept of Apache Airflow
  - DAG: Directed Acyclic Graph
  - Familiarizing with Cloud Composer
  - Building a data pipeline with Apache Airflow
  - Using the Taskflow API, PythonOperator, BashOperator, DummyOperator


    Workshop4_1:
      - Create a simple pipeline using task dependencies: T1 >> T2, where T1 prints "HELLO WORLD" and T2 prints the current date and time.
        After finishing the coding, copy the file from Cloud Shell to the DAGs bucket.
        Once you click on Airflow, it will display the DAGs (Directed Acyclic Graph) for the pipeline.
        The dependencies are defined as.
        t1 >> (t2,t3)
    
    Workshop4_1_Taskflow:
      - In Airflow 2.0 and above, It's the Taskflow API and used the Decorators in python, I used this API to code the same process as in workshop4_1.
        The pipeline consists of task dependencies where T1 prints "HELLO WORLD" and T2 prints the current date and time
        The dependencies are defined as.
        t1 >> (t2,t3)

    Workshop4_2:
      - This workshop help to understand how to fan out tasks, allowing multiple tasks to run concurrently after a single task completes
        T1 is 'Hello world.' After it has run completely, T2 and T3 will be running at the same time (in parallel). T2 is 'Print date,' and T3 checks the list of files
        in the GCP dags bucket.
        The dependencies are defined as.
        t1 >> (t2,t3)

    Workshop4_3:
      - This workshop helps to understand Task Dependencies and DAGs. I used the DummyOperator to simulate the DAGs in Airflow, making it faster than using PythonOperator or BashOperator.
        The dependencies are defined as
        [t[0], t[1], t[2]] >> t[4]
        [t[3], t[4], t[5]] >> t[6]
    
    Workshop4_3_w_loop:
      - This workshop is similar to Workshop4_3, but in this case, I used a loop to avoid creating multiple DummyOperators. You only need to specify the number required, and then run the loop.
        The dependencies are defined as
        [t[0], t[1], t[2]] >> t[4]
        [t[3], t[4], t[5]] >> t[6]

    Workshop4_4:
      - This workshop is similar to Workshop 1, but the difference is that we first use Cloud Shell to write our code, then import MySqlHook and edit the Airflow connection to enable connectivity to MySQL.
        T1 reads data from the database, T2 reads data from an API as a .CSV file, and T3 merges the data and uploads it to GCS.
        The dependencies are defined as
        [t1, t2] >> t3.

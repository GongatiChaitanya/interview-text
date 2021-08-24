# interview-text
details for interview


Introduction:

I am a cloud developer at FTD India Pvt Lmtd, where I have been working on Python, AWS Glue,Lambda, Dynamo, ETL, skills.
I graduated bachelors/btech in 2019 
Then i joined company as python developer and worked on AWS Lambda, Glue, S3, EC2, cloudwatch, Redshift, pyodbc, pandas, boto3, ELK skills.
and AWS IAM, secrets Manager services along with lambda, glue, and Nagios Monitoring tool for 10 months.

  aws lambda--is a server less compute service to run code without manageing servers its a even driven service.   

OVERALL :
	my top skills are Python, AWS (Lambda, Glue, DynamoDB, Redshift, S3, step function,kinesis, Athena) skills.
	I worked on Airflow, Docker, big SQL queries in my old projects.

  a. Created aws lambdas using serverless for S3 events .txt/.DAT/.zip from S3 to RDS database.
  b. Created splitting large files logic based on file row count and file row limit.
  c. Created spark Glue job to populate from one database to other database using crawlers, Glue connections, Glue databases, Glue tables, Glue bookmark in the Glue catalog.
  	print("reading from one DB")
    	DataSource0 = glueContext.create_dynamic_frame.from_catalog(database=job_config['source']['database'],
								table_name=job_config['source']['table_name'],
                                                                transformation_ctx="DataSource0")
	Transform0 = ApplyMapping.apply(frame=DataSource0, mappings=job_config["mappings"], transformation_ctx="Transform0")
	print("writing to other DB")
    	DataSink0 = glueContext.write_dynamic_frame.from_catalog(frame=Transform0, database=job_config['sink']['database'],
                                                             table_name=job_config['sink']['table_name'],
                                                             transformation_ctx="DataSink0")
  d. Worked on Spark ETL Glue scripts from snowflake db to S3 bucket using Glue S3 database, table and also Glue trigger
  e. Worked on Python-shell Glue job to move data from RDS database to S3 bucket.

  1. Developed and Automated IAM users validation/re-certification process using Python Boto3, AWS Code pipeline, nested Lambdas, 
     Secret Manager, RDS (Postgresql) services.
     	RDS DB -> EC2python script-> Snow-> API -> Lambda -> DB
     	code pipeline : Source (S3/codecommit) -> Build (code build) -> Deploy (ECS Fargate)
  
  2. Automated the servers (disks, services, cpu, memory) monitoring using Python nmap, multiprocesing, Nagios xi, Nagios core tool
     by Dynamically creating host, hostgroups, service checks respectively for all available servers.
     	Nagios -> ncpa -> host -> hostgroups -> device check -> servicegroup 
  
  3. Created ETL scripts for different (datasets) file formats like xml, xlsx, csv, json files using Python pandas, elasticsearch, pyspark, pyodbc,
     AWS S3, EC2/Glue/EMR, Redshift, IAM services.
     	S3/ES (csv, xlsx) -> EC2, PYTHON (boto3, pandas) -> S3 (pipe-delimited format file) -> REDSHIFT (Pyodbc) -> SPOTFIRE

  4. Created ETL scripts for different (datasets) file formats like xml, xlsx, csv, json files using Python , elasticsearch, pyspark, pyodbc,
     AWS S3, scheduling Glue, Crawler, Redshift, IAM services.
	S3/ES (csv, xlsx) -> Glue, PYTHON (boto3, pandas) -> S3 (pipe-delimited format file) -> REDSHIFT (Pyodbc) -> SPOTFIRE
	Memory related issues -> solution is to increase spark memory 
	# pandas wont work here, so need to use spark df and Glue dynamic df
  5. Created ETL scripts for different (datasets) file formats like xml, xlsx, csv, json files using Python pandas, elasticsearch, pyspark, pyodbc,
     AWS S3, EMR, Redshift, IAM services.
     	S3/ES (csv, xlsx) -> EMR, PYTHON (boto3, pandas) -> S3 (pipe-delimited format file) -> REDSHIFT (Pyodbc) -> SPOTFIRE
     a) •	Ingested server logs to elastic indices using Logstash, file beat, Kibana.
     b) •	Updated custom reports in Kibana application using angular JS, Elastic search.
  6. Converted images to thumbnails using AWS S3, Lambda, Cloudwatch, Python ffmpy (FFmpeg)
  	S3 -> LAMBDAS -> S3
  7. Created DAG files to monitor and schedule the jobs in Airflow
  	S3 -> EC2 (python) -> S3 -> Redshift
	https://github.com/BHAASKARR/Notes/blob/master/airflow
  8. Converted machine made zip files to ADF format files using AWS S3, Lambda, Flask API, ping federator(OAuth2).
  	S3 -> Lambda (ping federator-oauth2 token) -> flask API (validate bearer) -> call Jar file    
     
June 08, 2020:
Q: We concentrated only on business logic as we have support team to solve issues and spinning up new services EMR/EC2.

Q: What are the challenges faced while working on Glue"
	   # pandas wont work here, so need to use spark df and Glue dynamic df
	   IAM role 
	   To create an IAM role so that Glue can access all the required services securely
		Service: Glue, S3, Cloudwatch
		Permissions: 

	   The default number of tables returned by the boto3 Glue get_tables function is 100, but can be set to a max of 1000.
	   Iterating tables/catalogs 
	   https://www.linkedin.com/pulse/my-top-5-gotchas-working-aws-glue-tanveer-uddin/

Q: Can you list down the projects you did and technlogy used?
    a) Kibana dashboards - angular js, elasticsearch:  https://www.youtube.com/watch?v=1hIeysz5Uj
     	 Ingested server logs to elastic search using ELK and file beat 
    b) Datasets ETL projects (DVS, ICDATA, SYSTAG, PCMM)
       S3/ES (csv, xlsx) -> EC2, PYTHON (boto3, pandas) -> S3 (pipe-delimited format file) -> REDSHIFT (Pyodbc) -> SPOTFIRE
      removed config from files to database (so that we can update if we need without any extra docs, help from other deployment/support teams)
         ex: 
             1|1|257368|465569|41365|19950218|2-HIGH|0|17|2608718|9783671|4|2504369|92072|2|19950331|TRUCK
             1|2|257368|201928|8146|19950218|2-HIGH|0|36|6587676|9783671|9|5994785|109794|6|19950416|MAIL
    c) PAT dataset: xml files ,pyenv virtualenv, xmltodict, airflow 
        [S3 -> EC2 (python, pyenv) -> S3 -> Redshift ] -> Airflow
          wavelength uncertainity, wavelenth accuracy , lampcheck
           zip/xml,txt, roh -> json/txt metadata/raw files -> Redshift 
           raw  fact_table
           dimension dimension_table
           sumarized table
           lamp_poistion table
           json experiment_metadata
    d) Creating thumbnails for images : Docker
        S3 -> LAMBDAS -> S3
    e) Python2.7 to Python 3  : 2to3 library
    f) CMT dataset : multiple .txt files using pandas, airflow 
       S3 -> EC2 (python) -> S3 -> Redshift
    g) ADF converter:
        convert machines created zip files to ADF files
        S3 -> Lambda (ping federator-oauth2 token) -> flask API (validate bearer) -> call Jar file    
    h) hygieia : validating iam users 
       RDS DB -> EC2python script-> Snow-> API -> Lambda -> RDS DB
    i) Nagios monitoring tool
       Nagios host -> ncpa ->python -> nagios
         Nagios -> ncpa -> host -> hostgroups -> device check -> servicegroup 
       
Q: what are the challenges you faced in the projects?
   a) Kibana dashboard reports:
      Enhance Customer reports in Kibana dashboard with 
      a) typeahead functionality and 
      b) also showing results with one elastic query instead of multiple elastic queries for each page in table. 
	    Being Python Developer and have less idea on front end development jQuery, angular js, npm.
	    Completed above work within weeks (dev to prod) as I have less time to set up my local environment.
	    I tried to develop above enhancements in dev environment directly where Kibana and elastic search are configured.
	    After spending week,  I learned about different ways to develop typeahead functionality and then used code directly 
	    from developer forums. 
	    Implemented Grid table instead of current one, so now all query results will be stored in cache and then refine 
	    the results based on page number.

    b) Task : Upgrading ETL scripts from Python 2.7 to python 3.4/3.6/3.7
          Action : I used 2to3 library and then some manual correction after spending some time online.
              encoding concept while reading data or connecting to database
              Used 2to3 librarry # 2to3 file.py usage
              encoding not required as python3 default is utf-8.
                  1. division (/) 
                  In Python 2, / is integer division (assuming int inputs)
                  In Python 3, / is float division
                  In both 2 and 3, // is integer division
                  (To get float division in Python 2 requires either of the operands be a float, either as 20. or float(20))
                    >> 2/3 = 0 in python 2.7
                    >> 2/3 = 0.666 in python 3.7
                    >> 2//3 = 0 in python 3.7
                                 decode('utf-8') <-
                  2. strings <--------------------> bytes in Python3
                                   ->encode('utf-8')
                       unicode, strings in python2
          Result : Team is very happy as manual work is less.
  
    c) Challenge : how to get all host ipaddresses to create dynamic hosts, sg, services 
       i) devss/on-prem:
          Used nmap to scan through ports 5693 (ncpa) to get all hosts from subnet 
          ex: nmap -sT {onprem_SUBNET} -p 5693 -oX scan-xml.xml
       ii) aws ec2 instances:
           get list from aws EC2 instances or use nmap
    d) xml files - PAT - virtualenv
    	PAT(xmt), CMT(.txt)
    e) Nagios or AWS Lambda (why nested)? 
       flask rest api federated - adf converter api oath2(ping federator) - docker container
       
Q: what you did when you need clarification on the requirements? (Daily follow up to meet requirements) or
  how you handle challenges ?
A: I have sent meeting invitation to the team to discuss about approaches for dynamically create service_checks, hostgroups, hosts 
  using nmap subnets and ncpa agent
  
Q: what is the time you got a chance showcase your abilities? Manager impressed?
A: I have written pseudo code to automate nagios (dynamically create groups) for any hosts with minimal inputs and discussed this
    to manager with time complexity.
    
Q: How would you track your work ?
A: I will note down my daily tasks in one-note respectively 
      project - in page
        main requirements
        errors
        useful stuff
      meeting notes - in another page
      daily tasks - in new page
    
      
++++++++++++++++++++++++++++++++++
    Big companies Interview difference on 
        Software development/enginner; Big data developer or data engineer.
        online assessment; Phone interview
        Phone interview; Phone interview
        full-day interviews
    Data engineer:
       SQL - Datawarehouse concepts, data modelling and design. 
             columnar(AWS Redshift
       Python, 
       Spark for batch processing (for evry day), sparkstreaming for micro batches (for every min)
        Airflow for scheduling tasks and managing task dependencies (e.g. I only want to run the “generate revenue report” 
          task after I’ve run the “process sales” task for today).
      
++++++++++++++++
	Why we used below over other ?
	1. nested lambdas for users/roles/policies
	2. Nmap (Network mapper) to discover hosts (on-prem/ec2):
		Usecase: To discover new hosts and running services
		 Nmap to identify what devices are running on their systems, discovering hosts that are available and the services 
		 they offer, finding open ports and detecting security risks
		Fot both windows, linux and on-prem/cloud
		nmap -sT {SUBNET} -p5693 -oX scan-xml.xml or # sT: TCP connect port scan -p:specify a port or port range	
		nmap -oX - -p 5693 -sV -T5 -open 11.118.40.0/24
		nmap -p 5693 CIDR
	3. Multiprocessing library	
	4. Why flask over django?
		a. Flask lightweighted
		b. Easy to create simple web framework
	5. Why flask restful api over flask plain api
	6. Why lambda over batch ?
		a. Easily triggerable with any sources
		b. Configurable
		c. Server less
	7. Why elk over splunk to solve log management issues for Analaytics
		Use case:  Ingested server logs to elasticsearch indices using Logstash, file beat, Kibana.
		a. Open source
		b. Elasticsearch (distributed RESTful search/analytics engine), Logstash (a data processing pipeline), and 
		   Kibana (for data visualization). Only recently did Beats (agent-based, single-purpose data shipping) join the stack.
		From <https://www.upgrad.com/blog/splunk-vs-elk/> 
	8. Why redshift ?
		Usecase: to access data for analytics
		A. Columnar storage : Amazon Redshift transparently converts the data to columnar storage for each of the columns.
		B. https://docs.aws.amazon.com/redshift/latest/dg/c_columnar_storage_disk_mem_mgmnt.html
		Simple and cost effective to run high performance queries like Petabytes of structured data. 
		So that we can build powerful and cost effective reports and dashboards using existing business intelligence tools


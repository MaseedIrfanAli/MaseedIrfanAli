from docx import Document
from docx.shared import Pt
from docx.enum.text import WD_PARAGRAPH_ALIGNMENT
from docx.oxml.ns import qn
from docx.oxml import OxmlElement

# Load content from the textdoc
resume_text = """
Maseed Irfan Ali
📧 irfandataengineer@gmail.com | 📞 +91 9493925490 | 🌍 LinkedIn: https://www.linkedin.com/in/maseed-irfan-ali/

TECHNICAL SKILLS
▪ Programming Languages: Python, SQL, Shell Scripting
▪ Data Engineering & Big Data: Apache Beam, Spark, PySpark, Kafka, Hadoop
▪ Cloud Platforms: Google Cloud Platform (GCP), AWS
▪ Workflow Orchestration: Apache Airflow, Control-M Scheduler
▪ Containers & DevOps: Kubernetes (CKA certified), Docker, Flex Templates, Wrapper Scripts
▪ Databases & Warehouses: MySQL, PostgreSQL, Oracle, Snowflake, BigQuery
▪ ETL Tools: Informatica PowerCenter
▪ Version Control & Tracking: Git, JIRA

PROFESSIONAL EXPERIENCE
Data Engineer – CoreLogic (Sep 2023 – Mar 2024)
- Migrated batch Informatica ETL jobs to Python-based Apache Beam pipelines using GCP Dataflow.
- Utilized Airflow for DAG scheduling and workflow orchestration.
- Troubleshot Dataflow executions using Flex Templates and wrapper scripts.
- Built custom Python scripts to modernize data pipelines.
- Completed CKA course (KodeKloud) and deployed Kubernetes clusters on GCP and AWS.

Associate – CoreLogic (via NTT Data) (Jan 2022 – Sep 2023)
- Migrated 200+ scheduled workflow jobs from Informatica to GCP.
- Deployed 50+ new ETL workflow jobs on GCP using Compute Engine and Cloud Storage.
- Tools: Python, Informatica PowerCenter, Shell Scripting, PostgreSQL, MySQL, JIRA, Control-M.

ETL Developer – CoreLogic (Mar 2020 – Dec 2021)
- Developed 60+ ETL jobs for MySQL, Oracle, and DB2; outputs to GCP buckets.
- Automated workflows with Control-M Scheduler and Python scripting.

ETL Developer – CoreLogic (Mar 2019 – Feb 2020)
- Built and maintained 50+ ETL jobs for flat files, Excel, Oracle, Sybase, and SQL Server.
- Specialized in key Informatica transformations.

Trainee – Cognizant (Jul 2018 – Feb 2019)
- Completed training in Informatica PowerCenter and Oracle PL/SQL.

PROJECTS
- Kafka + MongoDB Ingestion: Real-time pipeline with Python Kafka producers/consumers.
- Kafka to MongoDB with Spark Streaming: Used PySpark to join and ingest Kafka order/payment streams.
- Spark + Kafka Pipelines: Stateful/stateless PySpark pipelines with real-time event processing.
- Snowflake CDC: Change data capture with dynamic tables and Snowpipe.

CERTIFICATIONS
- Certified Kubernetes Administrator (CKA) – Nana/KodeKloud
- GCP Dataflow & Apache Beam – Udemy
"""

# Create Word document
doc = Document()
doc.add_paragraph("Maseed Irfan Ali", style='Title')
doc.add_paragraph("📧 irfandataengineer@gmail.com | 📞 +91 9493925490 | 🌍 LinkedIn: https://www.linkedin.com/in/maseed-irfan-ali/")

for line in resume_text.split('\n')[3:]:
    doc.add_paragraph(line)

# Save file
file_path = "/mnt/data/Maseed_Irfan_Resume.docx"
doc.save(file_path)

file_path

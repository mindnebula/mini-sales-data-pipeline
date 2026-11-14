# Project Overview

## 1. Project Information

| Attribute | Description |
|---|---|
| Project Name | Mini Sales Data Pipeline |
| Project Type | Educational Data Engineering Project |
| Domain | E-commerce |
| Status | In Progress |

## 2. Project Description

Mini Sales Data Pipeline is an educational project designed to automate the processing of e-commerce sales data.

The system extracts data from CSV files, transforms and validates it using Python, and loads the processed data into a PostgreSQL database.

The processed data is used for SQL-based business analytics and sales reporting.

A lightweight web interface built with Streamlit is planned for pipeline monitoring and data visualization.

## 3. Project Goal

To develop an automated ETL pipeline that ensures reliable processing, validation, and storage of e-commerce sales data.

## 4. Project Scope

**In Scope:**
- Processing customer, product, and order data from CSV files.
- Data extraction, transformation, and validation.
- Loading data into PostgreSQL.
- Preventing duplicate records.
- Logging pipeline execution.
- SQL-based sales analytics.
- Data visualization using Streamlit.

**Out of Scope:**
- Development of a full e-commerce platform.
- Online payment processing.
- User authentication.
- Real-time data processing.
- Distributed processing with Apache Spark or Kafka.

## 5. Stakeholders

- **Data Pipeline Operator** — runs the pipeline and monitors its execution.
- **Business Analyst** — analyzes sales data and reviews business metrics.

## 6. Technology Stack

- Python
- Pandas
- PostgreSQL
- SQLAlchemy
- SQL
- pytest
- Streamlit
- Git and GitHub

## 7. Project Constraints and Assumptions

- Input data is provided in CSV format.
- Datasets contain synthetic data.
- PostgreSQL runs locally during initial development.
- Data processing is performed in batches.
- The ETL pipeline operates independently of the web interface.

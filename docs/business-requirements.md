# Business Requirements

## 1. Business Context

E-commerce businesses generate data about customers, products, and orders. This information is often stored in separate files or systems.

Manual processing of such data can be time-consuming and may result in duplicate, inconsistent, or incomplete records.

The project aims to demonstrate how an automated data pipeline can improve data processing and make information more accessible for business analysis.

## 2. Business Problem

The main business problems addressed by the project are:

- Manual data processing requires additional time and effort.
- Data from different sources is difficult to combine.
- Duplicate and invalid records reduce data reliability.
- Preparing sales reports requires additional data processing.
- Inconsistent data can lead to inaccurate analytical results.

## 3. Business Objectives

| ID | Business Objective |
|---|---|
| BO-01 | Reduce manual effort required to process sales data. |
| BO-02 | Centralize customer, product, and order data. |
| BO-03 | Improve data quality and consistency. |
| BO-04 | Simplify access to sales information for business analysis. |
| BO-05 | Provide reliable data for sales reporting. |

## 4. Stakeholders and Their Needs

| Stakeholder | Business Need |
|---|---|
| Data Pipeline Operator | Automate data processing and monitor pipeline execution. |
| Business Analyst | Access consistent sales data and analyze business performance. |

## 5. Business Success Criteria

The project is considered successful when:

- Data from all defined CSV sources can be processed automatically.
- Processed data is stored in a centralized PostgreSQL database.
- Duplicate and invalid records are identified and handled.
- Sales data can be analyzed using SQL queries.
- Business users can access key sales metrics through analytical reports.

## 6. Business Rules

| ID | Business Rule |
|---|---|
| BR-01 | Each customer must have a unique identifier. |
| BR-02 | Each product must have a unique identifier. |
| BR-03 | Each order must belong to an existing customer. |
| BR-04 | Each order item must reference an existing order and product. |
| BR-05 | Order item quantity must be greater than zero. |
| BR-06 | Product and order item prices cannot be negative. |
| BR-07 | Cancelled orders must not be included in completed sales revenue. |
| BR-08 | Repeated pipeline executions must not create duplicate business records.

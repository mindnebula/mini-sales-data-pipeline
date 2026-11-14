# Functional Requirements

## 1. Introduction

This document defines the functional requirements for the Mini Sales Data Pipeline.

The requirements describe the system functionality, including data extraction, transformation, validation, loading, pipeline monitoring, and business analytics.

Each requirement has a unique identifier and acceptance criteria to support implementation and testing.

## 2. System Actors

| Actor | Description |
|---|---|
| Data Pipeline Operator | Starts the pipeline and monitors its execution. |
| Business Analyst | Uses processed data and analytical reports. |

## 3. Functional Requirements

### 3.1. Data Extraction

**FR-01. Customer Data Extraction**

The system shall read customer data from the `customers.csv` file.

Acceptance Criteria:
- The system reads all records from the file.
- The system identifies missing or unreadable files.
- Extracted records are passed to the transformation stage.

**FR-02. Product Data Extraction**

The system shall read product data from the `products.csv` file.

Acceptance Criteria:
- The system reads all records from the file.
- The system identifies missing or unreadable files.
- Extracted records are passed to the transformation stage.

**FR-03. Order Data Extraction**

The system shall read order data from the `orders.csv` and `order_items.csv` files.

Acceptance Criteria:
- The system reads records from both files.
- The system identifies missing or unreadable files.
- Extracted records are passed to the transformation stage.

### 3.2. Data Transformation and Validation

**FR-04. Data Type Conversion**

The system shall convert input values into the required data types before loading them into the database.

Acceptance Criteria:
- Date values are converted into a valid date format.
- Numeric values are converted into appropriate numeric types.
- Invalid values are identified and reported.

**FR-05. Required Field Validation**

The system shall verify that all required fields contain valid values.

Acceptance Criteria:
- Records with missing required values are identified.
- Invalid records are excluded from the loading stage.
- Validation results are recorded in the processing log.

**FR-06. Duplicate Detection**

The system shall identify duplicate records based on their business identifiers.

Acceptance Criteria:
- Duplicate customer IDs are identified.
- Duplicate product IDs are identified.
- Duplicate order IDs are identified.
- Duplicate records are not inserted into the database.

**FR-07. Business Rule Validation**

The system shall validate records according to the defined business rules.

Acceptance Criteria:
- Order references to non-existent customers are rejected.
- Order items referencing non-existent orders or products are rejected.
- Order item quantities must be greater than zero.
- Negative prices are rejected.

### 3.3. Data Loading

**FR-08. Data Loading into PostgreSQL**

The system shall load validated customer, product, order, and order item records into the corresponding PostgreSQL tables.

Acceptance Criteria:
- Valid records are inserted into the appropriate tables.
- Database constraints are maintained.
- The number of successfully loaded records is recorded.

**FR-09. Duplicate Prevention During Repeated Execution**

The system shall prevent duplicate business records when the pipeline is executed multiple times using the same input data.

Acceptance Criteria:
- Repeated execution does not create duplicate records.
- Existing records are handled according to the defined loading strategy.
- Database integrity is maintained.

**FR-10. Transaction Management**

The system shall use database transactions when loading related datasets.

Acceptance Criteria:
- Successful loading operations are committed.
- Failed loading operations are rolled back according to the transaction boundary.
- Partially loaded related datasets are not left in an inconsistent state.

### 3.4. Pipeline Monitoring and Error Handling

**FR-11. Pipeline Execution Logging**

The system shall record information about each pipeline execution.

Acceptance Criteria:
- Each execution has a unique identifier.
- The start time and finish time are recorded.
- The execution status is recorded.
- The number of processed and loaded records is recorded.

**FR-12. Error Handling**

The system shall capture and record errors occurring during pipeline execution.

Acceptance Criteria:
- Errors are recorded with a descriptive message.
- The execution status reflects pipeline failure when an unrecoverable error occurs.
- The system provides sufficient information to identify the failed processing stage.

### 3.5. Business Analytics

**FR-13. Sales Data Analysis**

The system shall provide SQL queries for analyzing sales data.

Acceptance Criteria:
- Sales revenue can be calculated by month.
- Top-selling products can be identified.
- Revenue can be calculated by product category.
- Top customers can be identified.
- Orders can be grouped by status.
- Cancelled orders are excluded from completed sales revenue.

### 3.6. Web Interface

**FR-14. Pipeline Dashboard**

The system shall provide a web interface for viewing pipeline execution information.

Acceptance Criteria:
- The interface displays pipeline execution status.
- The interface displays the number of processed and loaded records.
- The interface displays available data quality information.

**FR-15. Analytical Dashboard**

The system shall provide a web interface for visualizing sales analytics.

Acceptance Criteria:
- The interface displays monthly sales revenue.
- The interface displays top-selling products.
- The interface displays revenue by product category.

## 4. Requirement Priorities

The requirements are prioritized using the MoSCoW method.

| Priority | Meaning |
|---|---|
| Must Have | Essential functionality required for the initial version. |
| Should Have | Important functionality that can be implemented after the core pipeline. |
| Could Have | Additional functionality that improves the project. |
| Won't Have | Functionality excluded from the current version. |

| Requirement IDs | Priority |
|---|---|
| FR-01 – FR-12 | Must Have |
| FR-13 | Must Have |
| FR-14 – FR-15 | Should Have |

## 5. Requirement Traceability

Functional requirements are derived from the business objectives and rules defined in `business-requirements.md`.

Each requirement should be linked to its implementation and corresponding automated tests.

This ensures that the implemented functionality addresses the original business needs.

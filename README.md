# Aircraft Maintenance Data Warehouse & Business Analytics

This repository contains the documentation and scripts for a data warehouse project focused on aircraft maintenance data. The project was completed as part of the **BAIT 3003 Data Warehouse Technology** course at Tunku Abdul Rahman University College.

## Table of Contents
1. [Project Overview](#project-overview)
2. [Project Team](#project-team)
3. [Project Structure](#project-structure)
   - [Chapter 1: Data Warehouse Design](#chapter-1-data-warehouse-design)
   - [Chapter 2: ETL Process](#chapter-2-etl-process)
   - [Chapter 3: Business Analytics Reports](#chapter-3-business-analytics-reports)
4. [Prerequisites](#prerequisites)
5. [Installation & Usage](#installation--usage)
6. [File Overview](#file-overview)
7. [License](#license)

## Project Overview

The primary goal of this project is to design and implement a data warehouse to analyze aircraft maintenance costs, technician performance, and operational trends. The system supports business analytics by providing insightful reports on various aspects of maintenance operations.

## Project Structure

### Chapter 1: Data Warehouse Design

- **Logical Design**: Implements a star schema with a central `MAINTENANCE_COST` fact table and the following dimensions:
  - `DATE_DIM`
  - `TECHNICIAN_DIM` (with SCD Type 2)
  - `AIRCRAFT_DIM`
  - `AIRPORT_DIM`

- **Physical Design**: SQL `CREATE TABLE` scripts defining data types, constraints, primary keys, and foreign key relationships.

### Chapter 2: ETL Process

- **Initial Loading**: Scripts for first-time population of dimension and fact tables from the source database.
- **Incremental Loading**: Scripts for subsequent data updates without disrupting existing records.
- **SCD Type 2**: Procedures to manage slowly changing attributes in `TECHNICIAN_DIM`, preserving historical records.

### Chapter 3: Business Analytics Reports

A suite of SQL queries and reports to analyze:

- Top 5 Airports by Maintenance Cost (with top 3 maintenance items breakdown)
- Yearly Maintenance Cost and Event Counts
- Comparative Analysis of Maintenance Items Across Years
- Aircraft Reliability Metrics (MTBF, MTTR, Availability) and Cost Trends by Model
- Top 10 Technicians by Average Wage Per Call

## Prerequisites

- Oracle Database (or compatible SQL-based RDBMS)
- SQL Client or IDE (e.g., SQL Developer, DBeaver)

## Installation & Usage

1. **Clone the Repository**
   ```bash
   git clone https://github.com/your_org/aircraft-maintenance-dw.git
   cd aircraft-maintenance-dw


2. **Configure Database Connection**

   * Update connection settings in the ETL scripts to match your environment.

3. **Create Schema & Tables**

   * Execute the `CREATE TABLE` scripts located in the `chapter1/design/` directory.

4. **Populate Data Warehouse**

   * Run the initial load scripts in `chapter2/etl/initial_load/`.
   * Schedule or invoke the incremental load scripts in `chapter2/etl/incremental/`.

5. **Generate Reports**

   * Use the SQL queries provided in `chapter3/reports/` to generate business analytics insights.

## File Overview
* **README.md**: Project overview and usage guidelines.
* **chapter1/**: Data warehouse design scripts and documentation.
* **chapter2/**: ETL process scripts (initial and incremental load).
* **chapter3/**: SQL reports and analytics queries.

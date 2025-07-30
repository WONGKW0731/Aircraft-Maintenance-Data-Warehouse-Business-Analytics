Below is a suggested GitHub README.md structure using your existing project description. You can copy this into your repository’s README.md and adjust any links or commands as needed.


# Aircraft Maintenance Data Warehouse & Business Analytics

This repository contains the documentation and scripts for a data‑warehouse project focused on aircraft maintenance data. The project was completed as part of the **BAIT 3003 Data Warehouse Technology** course at Tunku Abdul Rahman University College.

---

## Table of Contents

1. [Project Overview](#project-overview)  
2. [Team Members](#team-members)  
3. [Repository Structure](#repository-structure)  
4. [Data Warehouse Design](#data-warehouse-design)  
   - [Logical Design](#logical-design)  
   - [Physical Design](#physical-design)  
5. [ETL Process](#etl-process)  
   - [Initial Loading](#initial-loading)  
   - [Incremental Loading](#incremental-loading)  
   - [SCD Type 2 for TECHNICIAN_DIM](#scd-type-2-for-technician_dim)  
6. [Business Analytics Reports](#business-analytics-reports)  
7. [How to Use](#how-to-use)  
8. [Files](#files)  
9. [License](#license)  

---

## Project Overview

The primary goal of this project is to design and implement a data warehouse to analyze aircraft maintenance costs, technician performance, and operational trends. The system supports business analytics by providing insightful reports on various aspects of maintenance operations.

---

## Data Warehouse Design

### Logical Design

- **Fact Table:** `MAINTENANCE_COST`  
- **Dimension Tables:**  
  - `TECHNICIAN_DIM` (with SCD Type 2)  
  - `DATE_DIM`  
  - `AIRCRAFT_DIM`  
  - `AIRPORT_DIM`  

The schema follows a star‑schema model optimized for query performance and analytic workloads.

### Physical Design

The `create_tables.sql` script defines:

- Column data types  
- Primary and foreign key constraints  
- Indexes for performance tuning  

---

## ETL Process

### Initial Loading

Use `etl_initial_load.sql` to perform the first‐time population of dimension and fact tables from the source system.

### Incremental Loading

Run `etl_incremental_load.sql` on a scheduled basis to append new maintenance records without impacting existing historical data.

### SCD Type 2 for TECHNICIAN_DIM

The `scd2_technician_dim.sql` script preserves history by inserting a new record whenever technician attributes change, using:

- Effective dates  
- Current‐flag indicators  

---

## Business Analytics Reports

The following SQL queries in the `reports/` folder generate key insights:

1. **Comparative Analysis of Maintenance Items**  
2. **Aircraft Reliability & Cost Metrics** (MTBF, MTTR, availability trends)
3. Comparative Report: Maintenance Cost & Utilization a year-over-year
4. **Top 5 Airports by Maintenance Cost**  
5. **Maintenance Cost & Event Count by Year**  
6. **Top 10 Technicians by Average Wage per Call**  

---

# Netflix Data Analysis with DBT

This project demonstrates an end-to-end data analysis pipeline for Netflix data using **DBT (Data Build Tool)**. It covers extraction, transformation, and loading (ETL) processes with a strong focus on building production-grade analytical data models.

---

## 📌 Project Overview

The project transforms raw Netflix datasets into structured, analytics-ready tables using DBT.
This enables scalable data modeling, automated testing, lineage tracking, and documentation — all essential components of modern data engineering and business intelligence workflows.

---

## 🚀 Key Features

* **DBT Core Implementation** — Modular SQL transformations with version control and reusability
* **Cloud Integration** — Raw data stored in AWS S3 and processed in Snowflake
* **Dimensional Data Modeling** — Creation of fact and dimension tables optimized for analytics
* **Automated Data Testing** — Built-in DBT tests to ensure data quality and integrity
* **Data Lineage & Documentation** — Interactive documentation generated via DBT Docs
* **Environment Isolation** — Python virtual environments used for dependency management

---

## 🛠️ Technologies Used

* DBT (Data Build Tool)
* Snowflake
* AWS S3
* Python
* SQL
* Visual Studio Code (or any preferred IDE)

---

## Architecture Overview


<img width="2026" height="642" alt="Netflix diagram final" src="https://github.com/user-attachments/assets/20f7b389-4eab-4a98-83ec-c8a3695f6f91" />


The project follows a modern ELT analytics engineering architecture.

Raw Netflix datasets are first stored in Amazon S3, acting as the landing zone for immutable source data.
Data is then ingested into Snowflake, where transformations are performed using dbt.

The transformation layer standardizes raw data through staging and intermediate models before producing analytics-ready dimensional marts. Slowly Changing Dimension (SCD Type 2) logic is implemented using dbt snapshots to preserve historical changes.

Data quality is enforced through automated dbt tests, while lineage and documentation provide transparency and maintainability.
The final analytics marts enable dashboarding, ad-hoc analysis, and business reporting.

---

## 📂 Project Structure

```
models/        -> Transformation logic (staging + dimensional models)
seeds/         -> Static CSV datasets loaded directly into the warehouse
macros/        -> Reusable SQL macros
snapshots/     -> Slowly Changing Dimension (SCD) tracking
analysis/      -> Analytical queries for exploration
tests/         -> Data quality validations
dbt_project.yml -> DBT project configuration
profiles.yml    -> Warehouse connection configuration
```

---

## ⚙️ Getting Started

### ✅ Prerequisites

* AWS account with S3 access
* Snowflake account
* Python installed
* Git installed
* Preferred IDE (VS Code recommended)

---

## 🔧 Setup Instructions

### 1. Clone Repository

```
git clone https://github.com/darshilparmar/dbt-databuildtool--masterclass-netflix-project.git
cd dbt-databuildtool--masterclass-netflix-project
```

---

### 2. Create Virtual Environment

```
python -m venv dbt-env
```

Activate environment:

**Linux / Mac**

```
source dbt-env/bin/activate
```

**Windows**

```
dbt-env\Scripts\activate
```

---

### 3. Install DBT Snowflake Adapter

```
pip install dbt-snowflake
```

---

### 4. Configure AWS S3

* Create an S3 bucket (e.g., `netflix-data-bucket`)
* Generate AWS Access Key ID and Secret Access Key with appropriate permissions

---

### 5. Configure Snowflake

* Create a dedicated DBT user and role
* Create a warehouse (e.g., `COMPUTE_WH`)
* Create a database and schema for raw data storage

---

### 6. Initialize DBT Project

```
dbt init Netflix
```

Follow prompts to configure Snowflake connection details.

---

## ▶️ Running DBT

```
dbt seed          # Load seed datasets
dbt run           # Execute models
dbt test          # Run data quality tests
dbt docs generate # Build documentation
dbt docs serve    # Launch documentation site
```

---

## 📊 Outcome

This project demonstrates practical implementation of:

* Modern ELT with DBT
* Cloud-native data warehousing
* Analytics-ready dimensional modeling
* Automated data quality monitoring
* Data lineage and documentation best practices

---

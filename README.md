# Senior Data Engineer Technical Assessment

## Overview
This technical assessment is designed to evaluate your data engineering skills through a practical healthcare data processing scenario. You'll be building a data pipeline to process and analyze patient monitoring data from multiple hospitals.

**Time Allocation**: 3 hours

## Problem Statement
MedAnalytics Inc. processes monthly patient monitoring data from multiple hospitals. Your task is to design and implement a batch processing pipeline that handles vital signs measurements and lab results data, making it suitable for research and analysis purposes.

## Data Description

The pipeline will process two main datasets:

### Vital Signs Data (`vitals_2024.csv`)
```csv
hospital_id,measurement_date,patient_id,vital_type,value,unit
H001,2024-01-15,P12345,blood_pressure_systolic,120,mmHg
H001,2024-01-15,P12345,blood_pressure_diastolic,80,mmHg
H001,2024-01-15,P12345,heart_rate,72,bpm
```

### Lab Results Data (`lab_results_2024.csv`)
```csv
hospital_id,test_date,patient_id,test_type,result_value,reference_range,unit
H001,2024-01-16,P12345,glucose,95,70-100,mg/dL
H001,2024-01-16,P12345,cholesterol,180,125-200,mg/dL
```

## Task Requirements

### 1. Architecture Design (30 minutes)
- Design a batch processing architecture diagram
- Document the data flow from ingestion to final storage
- Include considerations for:
  - Data quality validation
  - Transformation logic
  - Error handling
  - Storage strategy

### 2. Implementation (2 hours)
Implement a proof-of-concept pipeline that includes:

#### Data Processing
- Data loading and validation
- Data transformation logic
- Monthly statistics calculation
- Data quality checks implementation

#### Pipeline Development
- Create an Airflow DAG with the following tasks:
  - Data validation
  - Data transformation
  - Statistics calculation
  - Quality reporting
- Include unit tests
- Implement error handling

### 3. Documentation (30 minutes)
- Solution architecture explanation
- Setup and running instructions
- Data quality approach
- Future improvements

## Project Structure
```
healthcare_pipeline/
├── dags/
│   └── healthcare_processing.py
├── src/
│   ├── transformations.py
│   └── quality_checks.py
├── tests/
│   └── test_transformations.py
├── data/
│   ├── vitals_2024.csv
│   └── lab_results_2024.csv
└── requirements.txt
```

## Evaluation Criteria

### Code Quality (35%)
- Clean, maintainable code
- Proper error handling
- Python best practices
- Unit test coverage

### Architecture Design (30%)
- Data flow design
- Processing strategy
- Error handling approach
- Scalability considerations

### Technical Implementation (25%)
- Functional data pipeline
- Effective use of Airflow
- Data quality checks
- Transformation logic

### Documentation (10%)
- Clear documentation
- Architecture explanation
- Setup instructions

## Required Technologies
- Python
- Apache Airflow
- Data quality tools (Great Expectations or Pandera)
- Git

## Deliverables
1. Architecture diagram and design document
2. Working code in the provided project structure
3. Documentation including:
   - Setup instructions
   - Architecture explanation
   - Data quality approach
   - Future improvements

## Setup Instructions
1. Clone the repository
2. Create a virtual environment:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
3. Install dependencies:
   ```bash
   pip install -r requirements.txt
   ```
4. Initialize Airflow:
   ```bash
   airflow db init
   airflow webserver -p 8080
   ```

## Sample Data
Sample datasets are provided in the `data/` directory. Each file contains approximately 1000 records for testing purposes.

## Notes
- Focus on code quality and maintainability
- Document any assumptions made
- Consider error handling and edge cases
- Include comments explaining key decisions
- You may use any additional Python libraries if needed, but document them in requirements.txt

## Questions?
If you have any questions during the assessment, please reach out to the interviewer for clarification.

Good luck!
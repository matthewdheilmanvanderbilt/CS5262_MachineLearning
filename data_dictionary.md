| Feature | Description | Data Type |
| --- | --- | --- |
| id | A unique identifier for each sample. | integer |
| gender | Sex of the patient.  Values are 'Male', 'Female', or 'Other'. | string |
| age | Age of the patient.  Ages 2 and higher contain zero(0) for all decimal values.  Ages under 2 have decimal values indicating the age in years and months. | float |
| hypertension | Indicates if a patient has hypertension: 0 = patient doesn't have hypertension; 1 = patient has hypertension.  | integer |
| heart_disease | Indicates if the patient has heart disease: 0 = patient doesn't have heart disease; 1 = patient has heart disease. | integer |
| ever_married | Indicates if the patient has ever been, or is currently married. Values are 'Yes' or 'No'. | string |
| work_type | Type of work the patient performs.  Values are 'children' (raising children is full time), 'Govt_job' (works for the government), 'Never_worked' (never worked or raised children), 'Private' (works for a non-government organizations and not self employed) or 'Self-employed (owns a business or independent contractor). | string |
| residence_type | Residence type of the patient.  Values are 'Rural' or 'Urban' | string |
| avg_glucose_level | Patient's average glucose level in blood in mg/dL. | float |
| bmi | Patient's body mass index. | float |
| smoking_status | Smoking status of the patient: values are 'formerly smoked', 'never smoked', 'smokes' or 'Unknown'.  Unknown means the information is not known for this patient.  | string |
| stroke | Indicates if the patient ever had a stroke: 0 = patient never had a stroke; 1 = patient had a stroke. | integer |

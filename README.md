# HealthStat Hospital Efficiency Analysis with Power BI
![](https://github.com/yanny-alt/HealthStat-Hospital-Efficiency-Analysis-with-Power-BI/blob/main/Images/markus-frieauff-IJ0KiXl4uys-unsplash.jpg)
## Executive Summary

### Background of the Project
HealthStat, a consulting company, hired us to analyze anonymized data from hospitals in New York state. The aim was to uncover insights on hospital efficiency for patients undergoing elective hip replacement surgery. Using Power BI, we created an engaging dashboard to visualize our findings.

### Key Insights Categorized
- 151 hospitals in New York State performed the surgical procedure of interest.
- Over 26,000 discharges were recorded for the procedure.
- The average length of stay (LOS) for the procedure was 2.65 days, with significant variability between hospitals.
- Demographic data such as age and gender were examined, but key factors behind the variability in LOS are not yet understood.
- 151 hospitals in New York State performed the surgical procedure of interest.
- Over 26,000 discharges were recorded for the procedure.
- The average length of stay (LOS) for the procedure was 2.65 days, with significant variability between hospitals.
- Demographic data such as age and gender were examined, but key factors behind the variability in LOS are not yet understood.

### Business Recommendations
- Focus on hospitals with the highest costs and LOS for targeted efficiency improvements.
- Investigate hospitals with extreme illness severity and mortality risk for potential intervention strategies.
- Explore patient disposition processes to skilled nursing homes to reduce LOS.
- Consider specific strategies for hospitals in New York City due to their higher costs and LOS.

### Dashboard Screenshot

The Report has 3 Insightful pages - LOS Comparison, Cost Comparison, Hospital Profile 
![Link to The Interactive Dashboard](https://app.powerbi.com/view?r=eyJrIjoiN2I5MWM0OGEtM2ZjNi00MWM1LTk4NzItZDk0OGEyZTkyZmFhIiwidCI6IjQ5MWM2ZTNhLTA3MjItNDhmMi1iMDFhLWFhMzliODc0MGYxNiJ9&pageName=ReportSectionc8f7cde367890ee09338)

 **LOS Comparison Page**:
   ![](https://github.com/yanny-alt/HealthStat-Hospital-Efficiency-Analysis-with-Power-BI/blob/main/Images/HealthStat%20LOS%20Comparison%20Page.png)
 **Cost Comparison Page**:
   ![](https://github.com/yanny-alt/HealthStat-Hospital-Efficiency-Analysis-with-Power-BI/blob/main/Images/HealthStat%20Cost%20Comparison%20Page.png)
 **Hospital Profile Page**:
  ![](https://github.com/yanny-alt/HealthStat-Hospital-Efficiency-Analysis-with-Power-BI/blob/main/Images/Hospital%20Profile%20Page.png)
   


### Dataset Details
- **Data Source**: New York state-wide hospital discharge data for the year 2016
- **Patient Population**: Those with "Elective hip replacement surgery"
- **Key Attributes of Interest**:
  - `length_of_stay`: Length of stay for patients.
  - `total_costs`: Total costs associated with each inpatient stay.
You can source for the data [here](https://github.com/yanny-alt/HealthStat-Hospital-Efficiency-Analysis-with-Power-BI/blob/main/Data%20Sources/hospital_inpatient_discharges_totalhipreplacement.csv)

### Data Analysis

#### Initial Exploration
- **Number of Hospitals**: 151
- **Total Discharges**: 26,286
- **Average Length of Stay (LOS)**: 2.65 days

#### Calculated DAX Measures

## Total Discharges 
                        Total Discharges = COUNTROWS(hospital_discharges)
Counts the total number of hospital discharges.

## Total Hospitals
                        Total Hospitals = DISTINCTCOUNT(hospital_discharges[facility_id])
Counts the total number of distinct hospitals represented in the dataset.

## Average Cost per Discharge
                        Average Cost Per Discharge = DIVIDE(SUM(hospital_discharges[total_costs]),[Total Discharges])
Computes the average cost per discharge by dividing the total costs of hospital discharges by the total number of discharges.

## Average LOS Days
                        Average LOS Days = AVERAGE(hospital_discharges[length_of_stay])
Computes the average length of stay (LOS) days for patients across all facilities.

## % Var Average Cost per Discharge
                        % Var Average Cost per Discharge = 
                                                          DIVIDE(
                                                              ([Average Cost Per Discharge]-[Average Cost per Discharge ALL]),
                                                              [Average Cost per Discharge ALL]
                                                          )
Calculates the percentage variation in the average cost per discharge compared to the overall average cost per discharge across all facilities.

## % Var Average LOS Days
                        % Var Average LOS Days = 
                                                DIVIDE(
                                                    ([Average LOS Days]-[Average LOS Days ALL]),
                                                    [Average LOS Days ALL]
                                                )
Calculates the percentage variation in the average length of stay (LOS) days compared to the overall average LOS days across all facilities.

## Power BI Dashboard
The Power BI dashboard we created visually presents the key insights and metrics derived from the dataset. It allows stakeholders to interactively explore the data and gain a better understanding of hospital efficiency opportunities for elective hip replacement surgeries.

[Link to the Interactive Dashboard](https://app.powerbi.com/view?r=eyJrIjoiN2I5MWM0OGEtM2ZjNi00MWM1LTk4NzItZDk0OGEyZTkyZmFhIiwidCI6IjQ5MWM2ZTNhLTA3MjItNDhmMi1iMDFhLWFhMzliODc0MGYxNiJ9)

## Conclusion
In this case study, we successfully analyzed the New York state-wide hospital discharge data for elective hip replacement surgeries in 2016. Our Power BI dashboard provides actionable insights to HealthStat, enabling them to identify hospitals with potential efficiency improvements and make informed decisions.

Thank you for reading! Your feedback is appreciated.
                  

# Automated Daily Chiller Performance Dashboard System  

This repository demonstrates a complete automated workflow for generating **daily chiller performance reports** using IoT/EMS data, Power BI dashboards, and Power Automate pipelines.  
The demo uses fully anonymized data and dashboards while maintaining the original architecture and analytics logic.

---

##  Project Summary

This system automatically:

1. Extracts raw minute-wise chiller data  
2. Transforms & calculates KPIs (kW/TR, CT Approach, TR Delivery, etc.)  
3. Updates Power BI dashboards for multiple units  
4. Exports dashboards as PDFs through Power Automate  
5. Sends a consolidated email report every day  

This removes manual report creation and ensures quick visibility of plant performance.

---

## 📂 Repository Structure
├── README.md
├── sample_data/
│ └── sample_chiller_data.csv
│
├── dashboards/
│ ├── Unit-1_Demo.pdf
│ ├── Unit-3_Demo.pdf
│ ├── Unit-4_Demo.pdf
│ ├── Unit-7_Demo.pdf
│ └── Unit-12_Demo.pdf
│
├── power_automate_flow/
│ └── pipeline_overview.png
│
├── data_processing/
│ └── ETL_process_explained.md
│
└── images/
└── dashboard_sample_screenshot.png

---

## 📊 Dashboard KPIs Included

Each dashboard contains:

- Chiller Load (TR%)  
- Actual vs Committed kW/TR  
- TR vs Power Consumption  
- CT Approach Trend  
- Wet Bulb Temperature Profile  
- Total Run Time  
- Positive/Negative Minutes Split  
- Daily Energy Consumption (kWh)

---

##  ETL Pipeline Overview

Full explanation in:  
📄 `data_processing/ETL_process_explained.md`

### **Extract**
- Pull minute-wise EMS data  
- TR, kW, Baseline kW/TR, Wet Bulb, CT Approach  
- Multi-unit data collection  

### **Transform**
- Clean/reset missing values  
- Align timestamps  
- Compute derived KPIs (kW/TR, CT Approach, kWh, etc.)  
- Calculate positive/negative minutes  
- Prepare dashboard-ready tables  

### **Load**
- Import cleaned data into Power BI  
- Refresh visuals for all units  
- Export dashboards for automation  

---

## ⚙️ Power Automate Pipeline

Includes:

- **Daily Recurrence Trigger**  
- **Export to File (Power BI)** for each chiller unit  
- **Email automation** with all dashboards attached  

Flow diagram location:  
`power_automate_flow/pipeline_overview.png`

---

##  Dashboards Included (Demo Outputs)

These PDFs represent anonymized daily dashboard outputs:

- Unit-1 Demo  
- Unit-3 Demo  
- Unit-4 Demo  
- Unit-7 Demo  
- Unit-12 Demo  

They preserve the structure and KPIs of a real industrial monitoring system.

---

##  Skills Demonstrated

### **Data Analytics**
- Time-series analysis  
- KPI engineering  
- Energy benchmarking  
- Operational efficiency insights  

### **Data Engineering**
- ETL pipeline development  
- Automated dataset preparation  
- Handling multi-unit sensor data  

### **Business Intelligence**
- Power BI dashboard design  
- KPI storytelling  
- Multi-system visualization  

### **Automation**
- Power Automate workflow design  
- Automated report generation  
- Email scheduling & delivery  

---

## 📬 Contact  
For suggestions or collaboration, feel free to reach out via GitHub.

---

# End of README.md




# ETL Process – Daily Chiller Performance Analytics  
*(Extract → Transform → Load)*

This document explains the ETL workflow used to convert raw EMS/IoT chiller data into clean, structured inputs for Power BI dashboards.

The ETL pipeline is designed to support **daily automated reporting** across multiple chiller units.

---

# 🔍 1. Extract (Raw Data Collection)

Data is extracted from the EMS (Energy Management System) or SCADA in **1-minute intervals**.  
Typical raw dataset columns include:

- Timestamp  
- Chiller load (TR)  
- Power consumption (kW)  
- Committed performance baseline (kW/TR)  
- Wet bulb temperature  
- Cooling tower approach  
- Sensor parameters  

Key extraction notes:

- Data is pulled automatically at scheduled times  
- Multiple chillers are logged in parallel  
- Missing timestamps are possible and handled in transformation  

---

# 🔧 2. Transform (Cleaning + KPI Generation)

## 2.1 Data Cleaning
- Remove duplicate timestamps  
- Replace missing sensor values with previous valid readings  
- Ensure timestamp continuity  
- Convert data types (float, integer, datetime)  
- Remove negative or impossible values  

## 2.2 KPI Calculations

### A. Actual kW/TR
```
Actual kW/TR = Power (kW) / Load (TR)
```

### B. Positive & Negative Minutes
```
If Actual kW/TR ≤ Committed → Positive Minute  
Else → Negative Minute
```

### C. TR Delivered  
Direct cooling load delivered by the chiller.

### D. CT Approach
```
CT Approach = CT Outlet Temp – Wet Bulb Temperature
```

### E. Daily kWh
```
Daily kWh = Σ (kW per minute × 1/60)
```

## 2.3 Performance Metrics
- Total Run Minutes  
- Positive Minutes  
- Negative Minutes  
- % Time Above/Below Committed Performance  
- Daily Energy Consumption  
- Wet Bulb Trend  
- Tower Approach Trend  

---

# 📥 3. Load (Power BI Dataset Refresh)

After transformation:

1. Data is loaded into Power BI tables  
2. Dashboards are refreshed for each chiller  
3. Updated visuals are exported to PDF via Power Automate  

Power BI visuals include:

- KPI Cards  
- Trend Graphs  
- TR vs kW plots  
- Time split donut charts  
- Run time summaries  

---

# 🚀 ETL Automation

The ETL process is fully automated to ensure:

- No manual calculations  
- Consistent reporting  
- Timely daily insights  
- Scalable multi-unit monitoring  

---

# 📌 End of ETL Documentation

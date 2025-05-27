# WarehouseTracker

# ERPFlow: Automated Stock Monitoring and Alert System

This project demonstrates an end-to-end automated inventory monitoring and alerting system using Power BI and Power Automate. It is designed to help users track stock levels and receive timely alerts when products fall below the minimum threshold.

The solution is built using free-tier Microsoft services, operating on structured XLSX data that is converted to CSV for compatibility with Power Automate. The process is fully automated, from data ingestion to visualization and alert notification.

## Features

- Dashboard and reporting built using Power BI
- Automated stock-level monitoring using Power Automate
- Alert notifications sent when stock levels drop below the defined threshold
- Structured data source in XLSX format, processed as CSV for automation compatibility
- No paid Microsoft licenses required

## System Workflow

1. **Data Preparation**  
   The project uses a structured Excel file (`ERP_Combined.xlsx`) that contains sales and inventory data. The file is exported to CSV format to allow access through Power Automate under a free Microsoft account.

2. **Report Generation with Power BI**  
   Power BI is used to build reports and dashboards based on the uploaded Excel data. A card visual is created to show the number of products that fall below a defined stock threshold.

3. **Alert Automation with Power Automate**  
   Power Automate runs a scheduled flow daily. It reads the CSV file from OneDrive, parses each row, checks if `StockLevel < 5`, and sends an alert email for matching products.

4. **Automated Execution**  
   The process is scheduled to run without manual intervention. Any stock-level change reflected in the Excel/CSV file will trigger appropriate email alerts and refresh the Power BI dashboard on the next update cycle.

## Technical Components

- **Power BI Desktop / Web Service** for building and hosting reports
- **Power Automate** for scheduled file parsing and email alerting
- **OneDrive (Personal)** as the file host for CSV data
- **Excel / CSV** as the input format

## Flow Logic Overview

- Scheduled trigger (daily)
- Get file content from OneDrive (CSV)
- Split CSV by row
- For each row:
  - Parse columns
  - Check if `StockLevel < 5`
  - If condition is met, send an email alert with product and stock information

## Flow Diagram

The overall process is shown as a Visio diagram located in the visio folder. It includes all automation logic from file reading to condition checks and notifications.

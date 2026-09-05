# Azure Cost Visibility & Governance Dashboard

## Overview

The Azure Cost Visibility & Governance Dashboard is a cloud cost monitoring and governance solution built using Microsoft Azure, Azure Cost Management, Azure Blob Storage, Power BI, and DAX.

The project monitors Azure spending, analyzes costs across services and resource groups, tracks budget utilization, and provides automated budget threshold notifications.

The dashboard was initially developed using sample data because the Azure subscription had very little actual usage. It was later integrated with real Azure Cost Management export data stored in Azure Blob Storage and connected to Power BI for scheduled data refresh.

## Project Objectives

- Monitor Azure cloud spending
- Analyze costs by Azure service
- Analyze costs by resource group
- Track daily cost trends
- Monitor monthly budget utilization
- Calculate remaining budget
- Identify budget status
- Automatically export Azure cost data
- Automatically refresh the Power BI dashboard
- Receive alerts when spending reaches configured thresholds

## Architecture

### Cost Monitoring Pipeline

Azure Subscription
        ↓
Azure Cost Management
        ↓
Daily Cost Export
        ↓
Azure Blob Storage
        ↓
Power BI
        ↓
Power Query
        ↓
DAX Calculations
        ↓
Interactive Dashboard

### Budget Alert Pipeline

Azure Spending
        ↓
Azure Budget
        ↓
Threshold Monitoring
        ↓
50% / 80% / 100%
        ↓
Email Notification

## Technologies Used

| Technology | Purpose |
|---|---|
| Microsoft Azure | Cloud platform |
| Azure Cost Management | Cost and usage monitoring |
| Azure Blob Storage | Storage for exported cost data |
| Azure Budgets | Budget and threshold monitoring |
| Power BI Desktop | Dashboard development |
| Power BI Service | Dashboard publishing and scheduled refresh |
| Power Query | Data transformation |
| DAX | Calculations and data analysis |
| Git & GitHub | Version control and documentation |

## Dashboard Features

### Cost Monitoring

- Total Azure Cost
- Cost by Azure Service
- Cost by Resource Group
- Daily Cost Trend
- Subscription-level cost analysis

### Budget Monitoring

- Monthly Budget
- Budget Remaining
- Budget Utilization %
- Budget Status

### Interactive Analysis

The dashboard provides filters for:

- Service Name
- Resource Group
- Date

These filters allow users to interactively analyze Azure spending.

## Automation

### 1. Automated Cost Export

Azure Cost Management is configured to export cost and usage data to Azure Blob Storage on a daily basis.

Azure Cost Management
        ↓
Daily Cost Export
        ↓
Azure Blob Storage

This eliminates the need to manually download cost data.

### 2. Power BI Scheduled Refresh

Power BI is configured with a scheduled refresh so that newly available Azure cost export data can be loaded into the dashboard automatically.

New Azure Cost Data
        ↓
Blob Storage
        ↓
Power BI Refresh
        ↓
Updated Dashboard

### 3. Budget Threshold Alerts

Azure Budget alerts are configured at:

- 50% — Warning
- 80% — Cost Monitoring Alert
- 100% — Budget Limit Reached

When a configured threshold is reached, Azure sends an email notification to the configured recipient.

## DAX Calculations

DAX (Data Analysis Expressions) was used to create measures for budget monitoring.

### Budget Remaining

Budget Remaining =
[Monthly Budget] -
SUM('Real Azure Cost Export'[Cost])

### Budget Utilization

Budget Utilization % =
DIVIDE(
    SUM('Real Azure Cost Export'[Cost]),
    [Monthly Budget],
    0
)

### Budget Status

Budget Status =
IF(
    SUM('Real Azure Cost Export'[Cost]) <= [Monthly Budget],
    "Within Budget",
    "Over Budget"
)

## Data Flow

The complete cost monitoring data flow is:

Azure Services
      ↓
Azure Cost & Usage Data
      ↓
Azure Cost Management
      ↓
Automated Daily Export
      ↓
Azure Blob Storage
      ↓
Power BI Power Query
      ↓
Data Transformation
      ↓
DAX Measures
      ↓
Interactive Dashboard

The budget monitoring process runs separately:

Azure Spending
      ↓
Azure Budget
      ↓
Threshold Evaluation
      ↓
50% / 80% / 100%
      ↓
Email Alert

## Development Approach

### Phase 1 — Dashboard Development

The dashboard was initially developed using sample Azure cost data.

This allowed the Power BI visuals, filters, data model, and DAX calculations to be developed and tested while the Azure subscription had limited real usage data.

### Phase 2 — Real Azure Data Integration

The project was then connected to real Azure cost data.

Azure Cost Management was configured to automatically export cost data to Azure Blob Storage. Power BI was connected to the exported data through Power Query and configured for scheduled refresh.

This transformed the project from a dashboard prototype into a practical Azure cloud cost monitoring and governance solution.

## Key Learning Outcomes

This project provided hands-on experience with:

- Azure Cost Management
- Azure Budgets
- Azure Blob Storage
- Cloud cost monitoring
- Cloud cost governance
- Power BI
- Power Query
- DAX
- Data visualization
- Automated data exports
- Scheduled dashboard refresh
- Threshold-based alerting
- Azure troubleshooting
- Git and GitHub

## Security Considerations

No Azure credentials, access keys, passwords, connection strings, or other sensitive information are included in this repository.

Authentication credentials are managed through the appropriate Azure and Power BI credential management systems.

## Future Improvements

Potential future enhancements include:

- Cost anomaly detection
- Azure cost forecasting
- Azure Advisor cost optimization recommendations
- Advanced cost analysis
- Automated Microsoft Teams notifications
- Cost optimization recommendations
- Advanced Power BI analytics
- Infrastructure-as-Code deployment
- Automated reporting

## Repository Structure

Azure-Cost-Visibility-Dashboard/
│
├── README.md
│
└── Azure-Cost-Visibility-Dashboard.pbix

The Power BI file contains the dashboard, data model, Power Query transformations, and DAX measures.

## Resume Project Description

Azure Cost Visibility & Governance Dashboard | Azure, Power BI, DAX

- Built an interactive Power BI dashboard to monitor Azure spending and analyze costs by service, resource group, and date.
- Integrated Azure Cost Management with Azure Blob Storage using automated daily cost exports.
- Configured Power BI scheduled refresh to load newly available Azure cost data.
- Developed DAX measures for budget remaining, budget utilization, and budget status.
- Configured Azure Budget threshold alerts at 50%, 80%, and 100% with automated email notifications.
- Implemented a cloud cost monitoring pipeline using Azure Cost Management, Blob Storage, Power BI, Power Query, and DAX.

Skills: Azure Cost Management, Azure Blob Storage, Azure Budgets, Power BI, Power Query, DAX, Cloud Cost Governance, Data Visualization, Cloud Automation

## Author

Fauzan Sayeed

BTech Computer Science Engineering Student

### Areas of Interest

- Microsoft Azure
- Cloud Engineering
- Cloud Infrastructure
- DevOps
- Cloud Monitoring
- Cloud Cost Governance

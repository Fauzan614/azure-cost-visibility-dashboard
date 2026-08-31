# Azure Cost Visibility Dashboard

An interactive Power BI dashboard designed to monitor Azure spending, analyze service-wise costs, track budget utilization, and identify cost trends.

## 📊 Dashboard Features

- 💰 Total Azure Cost monitoring
- 📅 Monthly Budget tracking
- 💵 Budget Remaining calculation
- 📈 Budget Utilization percentage
- ✅ Budget Status monitoring
- 📊 Cost analysis by Azure Service
- 📈 Daily Cost Trend analysis
- 🗂️ Cost analysis by Resource Group
- 🔎 Interactive filters for Resource Group, Service Name, and Date

## 🛠️ Technologies Used 

- Microsoft Azure
- Azure Cost Management concepts
- Power BI Desktop
- DAX
- Data Visualization

## 🎯 Project Objective

The objective of this project is to provide a clear and interactive view of cloud spending. The dashboard helps users understand Azure costs across different services and resource groups while monitoring budget utilization.

🚀 Future Improvements
Connect with real Azure Cost Management data
Automate cost data exports
Store cost data in Azure Storage
Add automated refresh
Configure cost threshold alerts
Integrate additional cost optimization recommendations
👨‍💻 Author

## Fauzan Sayeed

BTech Computer Science Engineering Student | Aspiring Azure Cloud Engineer


## 📐 Key Calculations

```DAX
Budget Remaining =
MAX('Azure Cost Data'[Budget]) - SUM('Azure Cost Data'[Cost])


Budget Utilization % =
DIVIDE(
    SUM('Azure Cost Data'[Cost]),
    MAX('Azure Cost Data'[Budget]),
    0
)


Budget Status =
IF(
    SUM('Azure Cost Data'[Cost]) <= MAX('Azure Cost Data'[Budget]),
    "Within Budget",
    "Over Budget"
)
```
# Version 2 – Azure Integration

## ☁️ Real Azure Cost Data Integration

Version 2 extends the original Power BI dashboard by integrating Azure cloud services for automated cost data collection.

### Architecture

Azure Subscription  
↓  
Azure Cost Management  
↓  
Scheduled Cost Export  
↓  
Azure Blob Storage  
↓  
Power BI Dashboard  

### 🔄 Data Flow

1. Azure Cost Management collects subscription usage and cost information.
2. A scheduled export generates cost and usage data.
3. The exported data is stored in Azure Blob Storage.
4. Power BI can import and transform the exported data.
5. The dashboard visualizes cloud spending and budget metrics.

### ⚙️ Azure Services Used

- Azure for Students Subscription
- Azure Cost Management
- Azure Cost Management Exports
- Azure Blob Storage
- Azure Storage Account

### 📊 Version 2 Improvements

- Configured automated Azure Cost and Usage export
- Created Azure Blob Storage container for exported cost data
- Added a real Azure cost data query in Power BI
- Added Data Source Status indicator
- Added Last Dashboard Update indicator
- Added an Architecture & Data Flow page

> **Note:** The Azure subscription is newly created, so the initial real cost export may not yet contain usage rows. The Power BI dashboard continues to use sample data until real Azure usage data becomes available. The integration is configured for future real-data updates.

## 📁 Updated Project Structure

```text
azure-cost-visibility-dashboard/
│
├── Azure_Cost_Visibility_Dashboard.pbix
├── AZURE PROJECT 2 - REAL COST INTEGRATION.pbix
├── dashboard.png
├── dashboard-v2.png
├── architecture.png
└── README.md

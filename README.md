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

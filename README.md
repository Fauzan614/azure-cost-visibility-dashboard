# Azure Cost Visibility & Governance Dashboard

## 📌 Overview

The **Azure Cost Visibility & Governance Dashboard** is a cloud cost monitoring and governance solution built using **Microsoft Azure, Azure Cost Management, Azure Blob Storage, Power BI, and DAX**.

The project is designed to monitor Azure spending, analyze costs across services and resource groups, track budget utilization, and provide automated budget threshold notifications.

The project initially used sample data for dashboard development and testing. It was later integrated with **real Azure Cost Management export data** and automated data ingestion through Azure Blob Storage.

---

## 🎯 Project Objectives

- Monitor Azure cloud spending
- Analyze costs by Azure service
- Analyze costs by resource group
- Track daily cost trends
- Monitor monthly budget utilization
- Calculate remaining budget
- Identify whether spending is within budget
- Automatically export Azure cost data
- Automatically refresh the Power BI dashboard
- Receive alerts when configured budget thresholds are reached

---

## 🏗️ Architecture

### Cost Monitoring Pipeline

```text
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

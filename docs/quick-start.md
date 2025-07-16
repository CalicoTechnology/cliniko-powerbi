# Quick Start Guide

This guide provides a quick introduction to get started with Cliniko Reports for Power BI.

## 1. Prerequisites

Before you begin, you need:

- Power BI Desktop (latest version)
- Cliniko account with API access
- Cliniko API key

## 2. Installation in 5 Minutes

### Step 1: Download the Report

1. Clone or download this repository
2. Extract files to a location on your computer

### Step 2: Open in Power BI Desktop

1. Open Power BI Desktop
2. Go to **File > Open**
3. Navigate to the extracted folder
4. Open `powerbi-project/calico-cliniko-base-reportpbip.pbip`

### Step 3: Configure API Connection

When you open the report for the first time it will prompt you for your API Key and Base Url and Timezone.

If you need to change these at a later date, you can configure the API connection:

1. In Power BI Desktop, click on **Transform data** in the Home ribbon
2. Go to **Transform data > Edit Parameters**
3. Update the following parameters:
   - **APIKey**: Your Cliniko API key
   - **API_BASE**: Your Cliniko subdomain (e.g., `https://api.{shard}.cliniko.com/v1`)
   - **TimezoneParameter**: Your local timezone (e.g., `Australia/Melbourne`)
4. Click **OK**

### Step 4: Refresh Data

1. Click **Refresh** in the Home ribbon
2. Wait for the data to load (first refresh may take several minutes)

## 3. Key Features

### Appointment Analysis

- Track total appointments
- Analyze no-shows and cancellations
- View appointment distribution by type, practitioner, and time

### Financial Insights

- Monitor revenue trends
- Track unpaid invoices
- Analyze product and service sales

### Practitioner Performance

- Compare practitioner workloads
- Track practitioner utilization
- Analyze revenue by practitioner

## 4. Basic Navigation

### Using Filters

- Use date filters to select time periods
- Filter by practitioner, appointment type, or business
- Use search fields to find specific information

### Interacting with Visuals

- Click on chart elements to filter other visuals
- Hover over data points for tooltips
- Use drill-down features where available

## 5. Next Steps

After setting up the basic report:

1. **Explore different report pages** using the tabs at the bottom
2. **Customize visuals** by clicking on them and using the format pane
3. **Create custom measures** if you need additional calculations
4. **Publish to Power BI Service** to share with your team (requires Power BI Pro)

## 6. Common Questions

**Q: How recent is the data?**
A: Data is as current as your last refresh. We recommend setting up a daily refresh schedule.

**Q: Can I add custom data?**
A: Yes, you can add custom tables and merge them with the existing data model.

**Q: Is patient data secure?**
A: The report uses your Cliniko API key which respects your security permissions. Never share reports with embedded credentials.

## 7. Getting Help

If you need assistance:

- Check the [User Guide](./user-guide.md) for detailed instructions
- See the [Troubleshooting Guide](./troubleshooting.md) for common issues
- Open an issue on GitHub for technical problems

## 8. Customization Tips

- **Add your logo**: Insert your practice logo in the report header
- **Change colors**: Use the format pane to match your brand colors
- **Add bookmarks**: Save specific views for quick access
- **Create mobile layout**: Configure for mobile viewing in Power BI Service

Happy reporting!

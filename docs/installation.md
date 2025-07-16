# Installation Guide

This guide walks you through the process of setting up Cliniko Reports for Power BI.

## Prerequisites

Before you begin, ensure you have:

1. **Power BI Desktop** - [Download from Microsoft](https://powerbi.microsoft.com/desktop/)
2. **Cliniko Account** - You must have a Cliniko account with API access
3. **Cliniko API Key** - Generated from your Cliniko account settings

## Installation Steps

### 1. Download the Reports

1. Clone the repository or download it as a ZIP file

   ```bash
   git clone https://github.com/yourusername/cliniko-reports.git
   ```
   
2. Extract the files to a folder on your computer

### 2. Open in Power BI Desktop

1. Open Power BI Desktop
2. Go to **File > Open**
3. Navigate to the folder where you extracted the files
4. Open `powerbi-project/calico-cliniko-base-reportpbip.pbip`

### 3. Configure API Connection

When you open the report for the first time it will prompt you for your API Key and Base Url and Timezone.

If you need to change these at a later date, you can configure the API connection:

1. In Power BI Desktop, click on **Transform data** in the Home ribbon
2. Go to **Transform data > Edit Parameters**
3. Update the following parameters:
   - **APIKey**: Your Cliniko API key
   - **API_BASE**: Your Cliniko subdomain (e.g., `https://api.{shard}.cliniko.com/v1`)
   - **TimezoneParameter**: Your local timezone (e.g., `Australia/Melbourne`)

4. Click **OK** to save the parameters

### 4. Refresh Data

1. Click on **Refresh** in the Home ribbon
2. The initial data load may take several minutes, depending on the size of your Cliniko data
3. If prompted, sign in with your Microsoft account or organizational account

### 5. Verify Installation

After the data has refreshed:

1. Check that your appointment data appears in the reports
2. Verify that the date filters work correctly
3. Ensure practitioner and business data is displayed correctly

## Troubleshooting

If you encounter issues during installation:

- **API Connection Issues**: Verify your API key and subdomain are correct
- **Refresh Errors**: Check the error messages in Power BI for specific details
- **Data Not Appearing**: Ensure your Cliniko account has data in the expected date ranges
- **Performance Issues**: For large datasets, consider implementing incremental refresh or limiting the data by date. 

For more troubleshooting help, see the [Troubleshooting Guide](./troubleshooting.md).

## Next Steps

Now that you have installed Cliniko Reports, you can:

- Explore the various report pages
- Customize visuals and filters
- Create your own measures and calculations
- Save and publish your report to Power BI Service

See the [User Guide](./user-guide.md) for more information on using the reports.

## Updates

To update to the latest version of Cliniko Reports:

1. Pull the latest changes from the repository

   ```bash
   git pull
   ```
   
2. Open the updated PBIP file in Power BI Desktop
3. Configure parameters as described above
4. Refresh your data

## Support

If you need help with installation, please:

1. Review this document and the [Troubleshooting Guide](./troubleshooting.md)
2. Check [GitHub Issues](https://github.com/yourusername/cliniko-reports/issues) for similar problems
3. Open a new issue if needed, with details about your installation problem

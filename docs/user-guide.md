# User Guide

This guide provides detailed instructions on using the Cliniko Reports in Power BI.

## Navigation

### Report Pages

The Cliniko Reports include several pages, each focusing on different aspects of your practice:

1. **Dashboard** - Overview of key metrics
2. **Appointments** - Detailed appointment analysis
3. **Practitioners** - Practitioner workload and performance
4. **Financial** - Revenue and invoicing analysis
5. **Products & Services** - Analysis of products and services sold

### Navigation Tips

- Use the tabs at the bottom of the Power BI window to switch between pages
- Click on elements in visuals to filter other visuals on the page
- Right-click on visuals for additional options
- Use the back button to return to previous views

## Filters and Slicers

### Common Filters

Each page includes filters for:

- **Date Range** - Select time periods for analysis
- **Practitioners** - Filter by one or multiple practitioners
- **Business/Location** - If you have multiple locations
- **Appointment Types** - Filter by specific service types

### Using Filters

1. **Basic Filtering**:
   - Click on values in visuals to filter the page
   - Use the filter pane on the right side of the screen

2. **Advanced Filtering**:
   - Click the dropdown on a filter for advanced options
   - Use "is", "contains", "greater than", etc. conditions
   - Create complex filters with "And/Or" logic

3. **Clear Filters**:
   - Click the eraser icon on slicers
   - Use the "Clear Filters" button when available
   - Right-click and select "Clear" on visual elements

## Key Visualizations

### Dashboard Page

- **Appointment Counter** - Total appointments with YTD comparison
- **Revenue Metrics** - Financial performance with trends
- **Practitioner Utilization** - Staff performance overview
- **Appointment Calendar** - Visual representation of scheduling

### Appointments Page

- **Appointments by Type** - Distribution of appointment types
- **Appointments by Day/Time** - Heatmap of busy periods
- **No-show Analysis** - Tracking of missed appointments
- **Duration Analysis** - Appointment length patterns

### Practitioners Page

- **Hours Worked** - Total hours by practitioner
- **Appointment Load** - Number of appointments handled
- **Revenue Generated** - Financial contribution
- **Practitioner Comparison** - Side-by-side performance metrics

### Financial Page

- **Revenue Trends** - Income over time with forecasting
- **Invoice Status** - Paid vs. unpaid invoice analysis
- **Payment Methods** - Analysis of payment types
- **Revenue by Service** - Income broken down by service type

### Products & Services Page

- **Top Products** - Best-selling items
- **Service Popularity** - Most frequently booked services
- **Price Analysis** - Average prices and discounts
- **Stock Analysis** - Inventory and restocking patterns

## Customizing Reports

### Basic Customizations

- **Resize Visuals** - Drag the corners to resize
- **Move Visuals** - Drag visuals to rearrange
- **Format Visuals** - Click the "Format" icon to change colors, fonts, etc.
- **Change Visual Types** - Use the Visualizations pane to switch chart types

### Adding Elements

1. **New Visuals**:
   - Click the visual type you want from the Visualizations pane
   - Drag fields from the Fields pane to the visual

2. **New Pages**:
   - Click the "+" at the bottom of the screen
   - Design your new page with visuals and filters

3. **Custom Measures**:
   - Right-click in the Fields pane and select "New Measure"
   - Write DAX formulas for custom calculations

## Data Refresh

### Manual Refresh

1. Click the "Refresh" button in the Home ribbon
2. Wait for all queries to complete
3. Check for any refresh errors in the notifications

### Scheduled Refresh

When published to Power BI Service:

1. Go to the dataset settings
2. Configure "Scheduled Refresh"
3. Set frequency (daily, weekly, etc.)
4. Ensure a gateway is configured if needed

## Exporting and Sharing

### Exporting Data

- **Export Visual Data**: Right-click on a visual and select "Export data"
- **Export Reports**: Use "Export to PDF" or "Export to PowerPoint" options
- **Export Raw Data**: Use "Show Data" option and then export to Excel

### Sharing Reports

1. **Within Power BI Desktop**:
   - Save the .pbix file and share it directly
   - Recipients will need their own API keys

2. **Via Power BI Service**:
   - Publish to Power BI Service
   - Share dashboards with specific users
   - Set up row-level security if needed

## Advanced Features

### Drill-Through

Some visuals support drill-through functionality:

1. Right-click on a data point
2. Select "Drill through"
3. Choose the target page for detailed analysis

### Bookmarks

Create and save specific views:

1. Configure filters and visual states
2. Go to the View menu and select "Bookmarks pane"
3. Click "Add" to save the current state
4. Use bookmarks to quickly switch between views

### What-if Parameters

For scenario analysis:

1. Go to Modeling tab
2. Select "New Parameter"
3. Configure parameter settings
4. Use in DAX measures for dynamic analysis

## Troubleshooting

### Visual Issues

- **Blank Visuals**: Check if filters are too restrictive
- **Error Messages**: Review the error text for specific issues
- **Performance Problems**: Consider simplifying complex visuals

### Data Issues

- **Missing Data**: Verify API connection and parameters
- **Incorrect Values**: Check calculations and measure definitions
- **Date Problems**: Ensure timezone settings are correct

For more help, see the [Troubleshooting Guide](./troubleshooting.md).

## Support Resources

- [Documentation](./README.md) - Full documentation index
- [GitHub Issues](https://github.com/yourusername/cliniko-reports/issues) - Report bugs or request features
- [GitHub Discussions](https://github.com/yourusername/cliniko-reports/discussions) - Community help and ideas

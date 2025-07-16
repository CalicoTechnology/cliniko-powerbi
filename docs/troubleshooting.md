# Troubleshooting Guide

This guide helps you diagnose and resolve common issues with Cliniko Reports for Power BI.

## API Connection Issues

### Authentication Failed

**Issue**: "Authentication failed" error when refreshing data

**Possible causes**:
- Invalid or expired API key
- Incorrect API URL

**Solutions**:
1. Generate a new API key in Cliniko (Settings > API)
2. Verify the API key is correctly entered in parameters (no extra spaces)
3. Check that you have API access permissions in Cliniko

### Too Many Requests

**Issue**: "Too many requests" error during refresh

**Possible causes**:
- Exceeding Cliniko's API rate limits (100 requests per minute)

**Solutions**:
1. Wait a few minutes and try again
2. Implement incremental refresh to reduce API calls
3. Contact Cliniko support to discuss rate limits

### Cannot Connect to Data Source

**Issue**: "Cannot connect to data source" error

**Possible causes**:
- Internet connectivity problems
- Cliniko API service disruption

**Solutions**:
1. Check your internet connection
2. Verify Cliniko service status
3. Try using a different network connection

## Data Issues

### Missing Data

**Issue**: Some data is not showing in reports

**Possible causes**:
- Date filters excluding relevant data
- Incorrect parameter configuration
- Data not yet in Cliniko system

**Solutions**:
1. Check date filters and expand if necessary
2. Verify API connection parameters
3. Ensure data exists in Cliniko for the selected time period

### Incorrect Values

**Issue**: Values don't match what you see in Cliniko

**Possible causes**:
- Time zone differences
- Currency formatting issues
- Data refresh timing

**Solutions**:
1. Check the `TimezoneParameter` setting
2. Verify currency formatting in measures
3. Perform a full refresh to get latest data

### Duplicate Records

**Issue**: Data appears to be duplicated

**Possible causes**:
- Multiple refreshes without proper clearing
- Issue with append queries

**Solutions**:
1. Clear the model cache (Transform Data > Clear Cache)
2. Check query steps for proper filtering
3. Implement distinct counts in measures

## Visual Display Issues

### Visuals Not Updating

**Issue**: Visuals don't update when filters change

**Possible causes**:
- Filter relationships not set correctly
- Issues with bidirectional filtering
- Visual requiring refresh

**Solutions**:
1. Check relationship settings in the model
2. Verify filter propagation settings
3. Try refreshing the visual or the whole report

### Labels Overlapping

**Issue**: Text labels overlap in charts

**Possible causes**:
- Too many data points
- Visual size too small

**Solutions**:
1. Increase visual size
2. Use "Fit to width" option for labels
3. Consider using a different visual type
4. Apply filters to reduce data points

### Slow Performance

**Issue**: Report is slow to interact with

**Possible causes**:
- Too much data loaded
- Complex calculations
- Too many visuals on one page

**Solutions**:
1. Implement query folding optimizations
2. Use calculated tables instead of calculated measures where appropriate
3. Split complex reports into multiple pages
4. Implement aggregations for large datasets

## Power BI Desktop Issues

### Out of Memory

**Issue**: "Out of memory" errors

**Possible causes**:
- Dataset too large for available RAM
- Too many columns or measures
- Inefficient data model

**Solutions**:
1. Remove unnecessary columns
2. Implement filtering at the query level
3. Consider using DirectQuery mode for very large datasets
4. Add more RAM to your computer

### Crashes During Refresh

**Issue**: Power BI Desktop crashes during data refresh

**Possible causes**:
- Memory limitations
- Corrupted file
- Software conflict

**Solutions**:
1. Close other applications to free memory
2. Update Power BI Desktop to the latest version
3. Try refreshing one table at a time
4. Rebuild the model from scratch if corruption is suspected

## Publishing Issues

### Cannot Publish to Power BI Service

**Issue**: Unable to publish to Power BI Service

**Possible causes**:
- Connectivity issues
- Authentication problems with Power BI Service
- File size too large

**Solutions**:
1. Check your internet connection
2. Verify Power BI Service login credentials
3. Reduce file size by removing unnecessary data
4. Check for Power BI Service outages

### Scheduled Refresh Fails

**Issue**: Scheduled refresh fails in Power BI Service

**Possible causes**:
- Data gateway issues
- Credential expiration
- API key rotation

**Solutions**:
1. Check gateway status and configuration
2. Update stored credentials
3. Verify API key is still valid
4. Check refresh history for specific error messages

## Common Error Messages

### "Expression.Error: The key didn't match any rows in the table"

**Possible causes**:
- Relationship based on non-existent values
- Lookup to empty table

**Solutions**:
1. Check relationship fields for matching values
2. Ensure lookup tables contain all referenced values
3. Implement error handling in calculated columns

### "DataSource.Error: Web.Contents failed to get contents"

**Possible causes**:
- API endpoint unreachable
- Invalid URL format
- Networking issues

**Solutions**:
1. Verify API URL parameters
2. Check network connectivity
3. Ensure API service is operational

### "Formula.Firewall: Query is accessing data sources that have privacy levels"

**Possible causes**:
- Mixed privacy levels in data sources
- Power BI security restrictions

**Solutions**:
1. Set consistent privacy levels for all sources
2. Enable "Ignore Privacy Levels" in Options (not recommended for sensitive data)
3. Restructure queries to separate external and internal data sources

## When to Contact Support

If you've tried the solutions above and still experience issues:

1. **Document the problem**:
   - Note specific error messages
   - Record steps to reproduce the issue
   - Take screenshots of the problem

2. **Gather system information**:
   - Power BI Desktop version
   - Windows version
   - Amount of RAM in your system

3. **Open an issue on GitHub**:
   - Provide all the details gathered above
   - Explain what you've already tried
   - Be responsive to follow-up questions

## Preventive Measures

To avoid issues in the future:

1. **Regular updates**:
   - Keep Power BI Desktop updated
   - Check for report updates on GitHub

2. **Backup your work**:
   - Save versions of your report
   - Export important visuals and data

3. **Performance monitoring**:
   - Use Performance Analyzer to identify bottlenecks
   - Monitor refresh times and data volumes

4. **Data governance**:
   - Document any customizations
   - Follow naming conventions for custom measures and columns

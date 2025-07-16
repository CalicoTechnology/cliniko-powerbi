# Data Model Documentation

This document provides an overview of the data model used in the Cliniko Reports for Power BI.

## Data Model Overview

The Cliniko Reports data model is built on data from the Cliniko API, with several transformed tables to support reporting and analysis. The model follows a star schema design with dimension and fact tables.

## Detailed Table Documentation

For comprehensive, user-friendly guides to each table, see the following detailed documentation:

### Primary Tables

- **[Patients Table Guide](./patients-table-guide.md)** - Complete guide to patient demographics, contact information, and metrics
- **[Appointments Table Guide](./appointments-guide.md)** - Detailed documentation for appointment scheduling, attendance, and performance data
- **[Practitioners Table Guide](./practitioners-guide.md)** - Information about healthcare providers, performance tracking, and team management

### Service and Product Catalogs

- **[Appointment Types Guide](./appointment-types-guide.md)** - Master catalog of appointment types, booking rules, and configuration
- **[Billable Items Guide](./billable-items-guide.md)** - Service and product catalog for billing and pricing management
- **[Products Guide](./products-guide.md)** - Inventory management, stock tracking, and product profitability

### Financial Data

- **[Invoices and Invoice Items Guide](./invoices-and-invoice-items-guide.md)** - Complete billing and financial analysis documentation


## Date and Calendar Tables

### DateTable

**Description**: A generated date table for time intelligence calculations.

**Key Fields**:

- `Date` - Calendar date
- `Year` - Calendar year
- `QuarterOfYear` - Quarter (1-4)
- `MonthOfYear` - Month (1-12)
- `DayOfMonth` - Day (1-31)
- `DayOfWeek` - Day of week (1-7)
- `DayName` - Day name (Monday, Tuesday, etc.)
- `MonthName` - Month name (January, February, etc.)
- `IsWeekend` - Whether the date is a weekend

### Appointment Calendar

**Description**: A specialized calendar table for appointment scheduling analysis.

**Key Fields**:

- `Date` - Calendar date
- `HourOfDay` - Hour (0-23)
- `TimeSlot` - 15-minute time slot
- `IsBusinessHour` - Whether the time slot is during business hours

## Calculated Tables

### Finance_Invoices

**Description**: Extended invoice analysis with additional calculations.

### Finance_InvoiceItems

**Description**: Extended invoice item analysis.

### Finance_Products

**Description**: Product analysis with sales metrics.

### Finance_BillableItems

**Description**: Analysis of billable items and services.

## Relationships

The data model includes the following key relationships:

1. **Appointments to Patients**: Many-to-one
2. **Appointments to Practitioners**: Many-to-one
3. **Appointments to AppointmentTypes**: Many-to-one
4. **Appointments to Businesses**: Many-to-one
5. **Invoices to Patients**: Many-to-one
6. **Invoices to Businesses**: Many-to-one
7. **InvoiceItems to Invoices**: Many-to-one
8. **InvoiceItems to Products**: Many-to-one (when applicable)
9. **InvoiceItems to Appointments**: Many-to-one (when applicable)
10. **All tables to DateTable**: Many-to-one on respective date fields

## Key Measures

The data model includes numerous calculated measures, including:

- **Total Appointments** - Count of appointments
- **Hours Worked** - Sum of appointment durations
- **Revenue** - Sum of invoice amounts
- **No-show Rate** - Percentage of appointments marked as no-shows
- **Appointment Utilization** - Percentage of available time slots filled

## Data Refresh Considerations

When refreshing data:

- **Incremental Refresh**: Configured for appointment data to minimize API calls
- **Complete Refresh**: Required for reference tables like practitioners and appointment types
- **History**: By default, the model loads two years of historical data

## Performance Optimization

The data model includes several optimization techniques:

- **Selective Columns**: Only necessary columns are imported
- **Data Types**: Proper data types are assigned to minimize memory usage
- **Aggregations**: Pre-calculated aggregations for common metrics
- **Bi-directional Filtering**: Limited to necessary relationships

## Limiting Data Volume

To reduce the amount of data imported and improve performance, you can apply filters when creating data queries:

### Query Parameters for Appointments

The data model supports optional query parameters to filter appointments data:

```m
// Get only cancelled appointments
CancelledAppointments = GetAllPagesByNextLink("appointments", "appointments", AppointmentType, "cancelled_at:*")

// Get only archived appointments
ArchivedAppointments = GetAllPagesByNextLink("appointments", "appointments", AppointmentType, "archived_at:*")

// Get appointments updated after a specific date
RecentAppointments = GetAllPagesByNextLink("appointments", "appointments", AppointmentType, "updated_at:>2024-01-01T00:00:00Z")

// Get appointments created after a specific date
NewAppointments = GetAllPagesByNextLink("appointments", "appointments", AppointmentType, "created_at:>2024-01-01T00:00:00Z")
```

### Common Query Patterns

- **Date Range Filtering**: Use `updated_at:>YYYY-MM-DDTHH:MM:SSZ` or `created_at:>YYYY-MM-DDTHH:MM:SSZ` to limit historical data
- **Status Filtering**: Use `cancelled_at:*` for cancelled appointments or `archived_at:*` for archived appointments
- **Combining Filters**: Multiple query parameters can be combined for more specific filtering

### Benefits of Data Limiting

- **Faster Refresh Times**: Reduced API calls and data transfer
- **Lower Memory Usage**: Smaller data model footprint
- **Improved Performance**: Faster report rendering and calculations
- **API Rate Limit Compliance**: Reduced risk of hitting Cliniko API limits

### Implementation Notes

- Query parameters are applied at the API level, reducing data transfer
- Some tables may require full refresh for referential integrity
- Consider business requirements when applying filters to avoid missing critical data
- Test filtered queries thoroughly to ensure all necessary data is included

## Extending the Model

To extend the data model:

1. Add new tables through Power Query
2. Create appropriate relationships
3. Add calculated columns and measures as needed
4. Test performance with representative data volumes
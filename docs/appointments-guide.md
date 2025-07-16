# Appointments Guide

## Overview

The Appointments table is the heart of your practice's scheduling system. It contains detailed information about every appointment that has been scheduled, including timing, attendance, cancellations, and outcomes. This table provides comprehensive insights into your practice's operations, patient behavior, and service delivery patterns.

## Basic Appointment Information

### Identification and Timing

| Field | Description | Example |
|-------|-------------|---------|
| **ID** | Unique identifier for each appointment | "APT-12345" |
| **Starts At** | Scheduled start date and time | "2024-03-15 09:00:00" |
| **Ends At** | Scheduled end date and time | "2024-03-15 10:00:00" |
| **Duration (Minutes)** | Length of appointment in minutes | "60", "30", "90" |
| **Duration** | Calculated duration from start/end times | "60" (minutes) |
| **Hours** | Duration converted to hours | "1.0", "0.5", "1.5" |
| **Appointment Date** | Date portion of appointment | "2024-03-15" |

### Appointment Details

| Field | Description | Example |
|-------|-------------|---------|
| **Name** | Title of the appointment | "Initial Consultation", "Follow-up" |
| **Description** | Detailed description of the appointment | "Comprehensive health assessment" |
| **Category** | Type classification of the appointment | "Consultation", "Treatment" |
| **Color** | Display color for calendar views | "#FF5733", "Blue" |

## Patient Attendance and Outcomes

### Attendance Tracking

| Field | Description | Values |
|-------|-------------|--------|
| **Patient Arrived** | Whether the patient showed up | Yes/No |
| **Did Not Arrive** | Whether the patient was a no-show | Yes/No |
| **Did Not Arrive Count** | Count for aggregating no-shows | 0 or 1 |
| **Completed Appointment** | Whether appointment was completed successfully | 0 or 1 |

### Treatment Documentation

| Field | Description | Values |
|-------|-------------|--------|
| **Treatment Note Status** | Status of clinical documentation | "Complete", "Pending", "Not Required" |
| **Invoice Status** | Billing status for the appointment | "Invoiced", "Pending", "Not Billable" |

## Cancellation Information

### Cancellation Details

| Field | Description | Example |
|-------|-------------|---------|
| **Cancelled At** | Date and time of cancellation | "2024-03-14 16:30:00" |
| **Cancellation Reason** | Reason code for cancellation | "Patient illness", "Practitioner unavailable" |
| **Cancellation Reason Description** | Detailed explanation | "Patient called in sick with flu symptoms" |
| **Cancellation Note** | Additional notes about cancellation | "Rescheduled for next week" |

### Cancellation Analysis

| Field | Description | Example |
|-------|-------------|---------|
| **Cancellation Lead Time** | Days between cancellation and appointment | "1", "7", "14" |
| **Cancelled Same Day** | Whether cancelled on appointment day | Yes/No |
| **Cancelled Same Day Count** | Count for aggregating same-day cancellations | 0 or 1 |

## Online Booking and Communication

### Booking Settings

| Field | Description | Values |
|-------|-------------|--------|
| **Show in Online Bookings** | Whether available for online booking | Yes/No |
| **Online Booking Policy Accepted** | Whether patient accepted online booking terms | Yes/No |
| **Max Attendees** | Maximum people who can attend | "1", "5", "10" |

### Communication Tracking

| Field | Description | Values |
|-------|-------------|--------|
| **SMS Reminder Sent** | Whether SMS reminder was sent | Yes/No |
| **Email Reminder Sent** | Whether email reminder was sent | Yes/No |

## Payment and Deposit Information

### Financial Settings

| Field | Description | Example |
|-------|-------------|---------|
| **Deposit Price** | Required deposit amount | "$50.00", "$25.00" |
| **Add Deposit to Account Credit** | Whether deposit becomes account credit | Yes/No |
| **Online Payments Enabled** | Whether online payment is available | Yes/No |
| **Online Payments Mode** | Payment processing method | "Immediate", "On completion" |
| **Online Bookings Lead Time (Hours)** | Minimum advance booking time | "24", "48", "72" |

### Telehealth Capability

| Field | Description | Values |
|-------|-------------|--------|
| **Telehealth Enabled** | Whether appointment can be conducted remotely | Yes/No |

## System References

### Related Records

| Field | Description | Purpose |
|-------|-------------|---------|
| **appointment_type.links.self** | Link to appointment type definition | Connect to service catalog |
| **patient.links.self** | Link to patient record | Connect to patient data |
| **practitioner.links.self** | Link to practitioner record | Connect to provider data |
| **business.links.self** | Link to business/location record | Connect to location data |

## Key Performance Metrics

### Appointment Volume Measures

| Measure | What It Shows | How It's Calculated |
|---------|---------------|-------------------|
| **Total Appointments** | Count of all appointments | Total number of appointment records |
| **Count of id YTD** | Year-to-date appointment count | Cumulative appointments from start of year |
| **Count of id YoY%** | Year-over-year percentage change | Current year vs. previous year comparison |
| **Count of id LY YTD** | Last year's YTD appointment count | Previous year same period |

### Time-Based Measures

| Measure | What It Shows | How It's Calculated |
|---------|---------------|-------------------|
| **HoursM** | Total appointment hours | Sum of all appointment durations in hours |
| **Hours YTD** | Year-to-date hours | Cumulative hours from start of year |
| **Hours YTD LY** | Last year's YTD hours | Previous year same period hours |
| **Hours LM** | Last month's hours | Previous month total hours |
| **Hours Chg** | Change from last month | Current month hours minus last month |

### Quality and Efficiency Measures

| Measure | What It Shows | How It's Calculated |
|---------|---------------|-------------------|
| **Cancellation Percentage** | Percentage of appointments cancelled | Cancelled appointments ÷ Total appointments × 100 |
| **Future Appointments** | Count of scheduled future appointments | Appointments with date >= today |
| **Future Practitioner Appointments** | Future appointments by practitioner | Filtered by practitioner and future dates |
| **MPVA2** | First appointment percentage | First appointments ÷ Total appointments |

## Understanding Appointment Status

### Appointment Lifecycle

1. **Scheduled**: Appointment is booked with start/end times
2. **Confirmed**: Patient has confirmed attendance
3. **Arrived**: Patient has checked in for appointment
4. **In Progress**: Appointment is currently taking place
5. **Completed**: Appointment finished successfully
6. **Cancelled**: Appointment was cancelled before completion
7. **No-Show**: Patient did not arrive for appointment

### Attendance Categories

- **Completed**: Not cancelled and patient arrived
- **Cancelled**: Has a cancellation date
- **No-Show**: Marked as "Did Not Arrive" = true
- **Scheduled**: Future appointments that haven't occurred yet

## Common Calculations

### Utilization Metrics

- **Appointment Utilization**: Scheduled hours ÷ Available hours
- **Completion Rate**: Completed appointments ÷ Total appointments
- **No-Show Rate**: No-shows ÷ Total appointments
- **Cancellation Rate**: Cancelled appointments ÷ Total appointments

### Revenue Analysis

- **Average Appointment Value**: Total revenue ÷ Number of appointments
- **Revenue per Hour**: Total revenue ÷ Total appointment hours
- **Practitioner Productivity**: Revenue per practitioner per hour

### Operational Efficiency

- **Same-Day Cancellation Rate**: Same-day cancellations ÷ Total cancellations
- **Booking Lead Time**: Average days between booking and appointment
- **Treatment Documentation Rate**: Completed notes ÷ Total appointments

## Relationships with Other Tables

### Core Relationships

- **Patients**: Each appointment belongs to one patient
- **Practitioners**: Each appointment is assigned to one practitioner
- **Appointment Types**: Each appointment has one type definition
- **Businesses**: Each appointment occurs at one location

### Financial Relationships

- **Invoices**: Appointments may generate invoices
- **Invoice Items**: Specific services may be billed per appointment

## Common Use Cases

### Scheduling Analysis

- **Peak Hours**: Identify busiest times of day/week
- **Practitioner Workload**: Compare appointment volume by practitioner
- **Service Demand**: Track popularity of different appointment types
- **Capacity Planning**: Analyze utilization for resource planning

### Patient Behavior Analysis

- **Attendance Patterns**: Track patient reliability
- **Cancellation Trends**: Identify cancellation patterns
- **Booking Preferences**: Online vs. phone booking analysis
- **Service Utilization**: Which services do patients use most

### Financial Performance

- **Revenue Trends**: Track appointment-driven revenue
- **Practitioner Performance**: Compare revenue by practitioner
- **Service Profitability**: Analyze revenue by appointment type
- **Collection Efficiency**: Track invoicing and payment patterns

### Operational Optimization

- **No-Show Reduction**: Identify and address no-show patterns
- **Reminder Effectiveness**: Analyze reminder success rates
- **Schedule Optimization**: Improve appointment scheduling efficiency
- **Resource Utilization**: Maximize practitioner and facility usage

## Tips for Using This Data

### Performance Monitoring

1. **Track Trends**: Monitor appointment volume over time
2. **Identify Patterns**: Look for seasonal or cyclical trends
3. **Benchmark Performance**: Compare current metrics to historical data
4. **Set Targets**: Establish goals for key performance indicators

### Quality Improvement

1. **Reduce No-Shows**: Implement strategies to improve attendance
2. **Optimize Scheduling**: Use data to improve appointment availability
3. **Enhance Communication**: Improve reminder and follow-up processes
4. **Streamline Operations**: Identify bottlenecks in appointment flow

### Financial Analysis

1. **Revenue Optimization**: Maximize appointment-driven revenue
2. **Cost Management**: Understand the cost of cancelled appointments
3. **Pricing Strategy**: Use utilization data to inform pricing decisions
4. **Profitability Analysis**: Identify most profitable services and practitioners

## Frequently Asked Questions

**Q: What's the difference between "Cancelled At" and "Did Not Arrive"?**
A: "Cancelled At" means the appointment was cancelled in advance, while "Did Not Arrive" means the patient didn't show up for a scheduled appointment.

**Q: How is appointment duration calculated?**
A: Duration is calculated from the difference between "Starts At" and "Ends At" times, converted to minutes or hours as needed.

**Q: What makes an appointment "completed"?**
A: An appointment is considered completed if it wasn't cancelled and the patient didn't fail to arrive.

**Q: How do I calculate the no-show rate?**
A: No-show rate = (Number of "Did Not Arrive" appointments ÷ Total appointments) × 100

**Q: What's a good cancellation rate?**
A: Industry benchmarks vary, but typically 5-10% is considered acceptable for healthcare practices.

**Q: How can I reduce same-day cancellations?**
A: Implement reminder systems, cancellation policies, and deposit requirements to encourage advance notice.

**Q: What's the purpose of the "First Appointment" flag?**
A: It helps identify new patient appointments for tracking patient acquisition and measuring patient value.

---

*This documentation helps you understand and analyze appointment data to improve your practice's efficiency, patient satisfaction, and financial performance.*

# Appointment Types Guide

## Overview

The Appointment Types table contains definitions for all the different types of appointments your practice offers. This table serves as the master catalog of services, defining the duration, pricing, booking rules, and payment options for each type of appointment. It's a reference table that other parts of your system use to ensure consistent appointment scheduling and billing.

## Basic Appointment Type Information

### Identification Fields

| Field | Description | Example |
|-------|-------------|---------|
| **ID** | Unique identifier for each appointment type | "APT-001" |
| **Name** | Name of the appointment type | "Initial Consultation", "Follow-up Visit" |
| **Description** | Detailed description of the appointment type | "Comprehensive assessment for new patients" |
| **Category** | Classification grouping for similar appointment types | "Consultation", "Treatment", "Assessment" |

### Visual and Scheduling Settings

| Field | Description | Example |
|-------|-------------|---------|
| **Color** | Color code for calendar display | "#FF5733", "Blue", "Green" |
| **Duration Minutes** | Standard length of appointment in minutes | "60", "30", "90" |
| **Max Attendees** | Maximum number of people who can attend | "1", "5", "10" |

## Online Booking Configuration

### Booking Availability

| Field | Description | Values |
|-------|-------------|--------|
| **Show In Online Bookings** | Whether patients can book this appointment type online | Yes/No |
| **Online Bookings Lead Time Hours** | Minimum hours advance notice required for online booking | "24", "48", "72" |

### Payment and Deposit Settings

| Field | Description | Example |
|-------|-------------|---------|
| **Online Payments Enabled** | Whether online payment is available for this appointment type | Yes/No |
| **Online Payments Mode** | How online payments are processed | "Immediate", "On completion", "Deposit only" |
| **Deposit Price** | Required deposit amount for booking | "$50.00", "$25.00", "$0.00" |
| **Add Deposit to Credit Account** | Whether deposit goes to patient's credit account | Yes/No |

## Modern Healthcare Features

### Telehealth Capability

| Field | Description | Values |
|-------|-------------|--------|
| **Telehealth Enabled** | Whether this appointment type can be conducted remotely | Yes/No |

## Understanding Appointment Type Settings

### Duration and Scheduling

- **Duration Minutes**: This is the default time slot length for this appointment type
- **Max Attendees**: For group appointments or when multiple people attend (family sessions, etc.)
- **Color**: Helps practitioners and staff visually distinguish appointment types in calendars

### Online Booking Rules

- **Show In Online Bookings**: Controls whether patients can self-book this appointment type
- **Lead Time Hours**: Prevents last-minute bookings that might not allow adequate preparation
- **Online Payments**: Determines if payment can be collected at time of booking

### Deposit Management

- **Deposit Price**: Can be used to secure appointments or reduce no-shows
- **Add to Credit Account**: If enabled, deposits become account credits rather than direct payments

## Common Appointment Type Categories

### Consultation Types

- Initial Consultation
- Follow-up Visit
- Review Appointment
- Telehealth Consultation

### Treatment Types

- Physiotherapy Session
- Massage Therapy
- Acupuncture Treatment
- Chiropractic Adjustment

### Assessment Types

- Health Assessment
- Diagnostic Evaluation
- Progress Review
- Outcome Measurement

### Administrative Types

- Documentation Review
- Insurance Consultation
- Treatment Planning
- Discharge Planning

## Relationships with Other Tables

The Appointment Types table connects to:

- **Appointments**: Each appointment is assigned one appointment type
- **Billable Items**: Appointment types may link to specific billable services
- **Practitioners**: Some appointment types may be practitioner-specific
- **Businesses**: Appointment types may be available at specific locations

## Common Use Cases

### Service Management

- **Service Catalog**: Maintain list of available services
- **Pricing Strategy**: Set consistent pricing across appointment types
- **Capacity Planning**: Use duration to plan practitioner schedules
- **Online Presence**: Control what services are available for online booking

### Operational Efficiency

- **Calendar Management**: Use colors and durations for efficient scheduling
- **Payment Processing**: Streamline billing with consistent appointment-service linking
- **Resource Allocation**: Plan staffing based on appointment type demand
- **Quality Control**: Ensure consistent service delivery across appointment types

### Financial Analysis

- **Revenue by Service Type**: Group appointments by type for revenue analysis
- **Popular Services**: Identify most frequently booked appointment types
- **Profitability Analysis**: Compare revenue to time invested by appointment type
- **Deposit Tracking**: Monitor deposit collection and conversion rates

## Configuration Best Practices

### Naming Conventions

1. **Use Clear Names**: "Initial Consultation" rather than "IC"
2. **Be Specific**: "60-min Massage" rather than just "Massage"
3. **Include Duration**: When multiple durations exist for same service
4. **Consistent Formatting**: Use the same naming pattern across all types

### Duration Settings

1. **Standard Increments**: Use 15, 30, 45, 60, 90 minute intervals
2. **Buffer Time**: Include time for notes and patient transition
3. **Realistic Estimates**: Base on actual service delivery time
4. **Consistency**: Same services should have same duration

### Online Booking Strategy

1. **Selective Availability**: Not all appointment types need online booking
2. **Appropriate Lead Times**: Balance convenience with preparation needs
3. **Deposit Requirements**: Use for high-value or high-no-show appointments
4. **Payment Timing**: Consider when payment collection works best

## Tips for Using This Data

### Service Analysis

1. **Duration Efficiency**: Monitor actual vs. scheduled appointment times
2. **Booking Patterns**: Track which appointment types are most popular
3. **Online vs. Phone**: Compare booking methods by appointment type
4. **Seasonal Trends**: Identify appointment type demand patterns

### Revenue Optimization

1. **Pricing Review**: Regularly assess appointment type pricing
2. **Deposit Strategy**: Use deposits strategically to reduce no-shows
3. **Online Payment**: Encourage online payment for cash flow
4. **Service Bundling**: Consider combination appointment types

### Operational Insights

1. **Practitioner Specialization**: Match appointment types to practitioner skills
2. **Capacity Planning**: Use duration data for resource planning
3. **Patient Flow**: Optimize appointment type sequences
4. **Quality Metrics**: Track outcomes by appointment type

## Frequently Asked Questions

**Q: How do I determine the right duration for an appointment type?**
A: Base it on the average time needed for the service, including preparation and documentation time. Monitor actual appointment times and adjust as needed.

**Q: Should all appointment types be available for online booking?**
A: No. Consider limiting online booking to routine appointments. Complex or assessment appointments may need phone booking for proper preparation.

**Q: How do deposits work with appointment types?**
A: Deposits can be required at booking time. They can either be applied to the final invoice or added to the patient's credit account for future use.

**Q: Can appointment types have different pricing?**
A: Yes, each appointment type can have different pricing. This is typically managed through linked billable items or during the invoicing process.

**Q: What's the purpose of the telehealth enabled setting?**
A: It indicates which appointment types can be conducted remotely via video call, which became important during COVID-19 and remains valuable for ongoing care.

**Q: How do I handle appointment types with variable durations?**
A: Create separate appointment types for different durations (e.g., "30-min Consultation" and "60-min Consultation") or use the most common duration as the default.

**Q: What happens if I change an appointment type's duration?**
A: Existing appointments keep their original duration, but new appointments will use the updated duration. Consider the impact on practitioner schedules.

---

*This documentation helps you understand and effectively manage appointment types in your Cliniko system. Proper configuration of appointment types ensures smooth operations, efficient scheduling, and accurate billing.*

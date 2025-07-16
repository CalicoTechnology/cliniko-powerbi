# Patients Table Guide

## Overview

The Patients table contains comprehensive information about all patients in your Cliniko system. This table serves as the central hub for patient demographics, contact details, preferences, and key metrics that help you understand your patient base.

## Patient Information Fields

### Basic Demographics

| Field | Description | Example |
|-------|-------------|---------|
| **Patient ID** | Unique identifier for each patient | "12345" |
| **First Name** | Patient's given name | "John" |
| **Last Name** | Patient's family name | "Smith" |
| **Preferred First Name** | Name the patient prefers to be called | "Johnny" |
| **Full Name** | Complete name (automatically combined) | "John Smith" |
| **Title** | Honorific title | "Mr", "Ms", "Dr" |
| **Date of Birth** | Patient's birth date | "1985-03-15" |
| **Age** | Current age in years (calculated automatically) | "40" |
| **Sex** | Biological sex | "Male", "Female" |
| **Gender Identity** | Self-identified gender | "Male", "Female", "Non-binary" |
| **Occupation** | Patient's job or profession | "Teacher", "Engineer" |

### Contact Information

| Field | Description | Example |
|-------|-------------|---------|
| **Email** | Primary email address | john.smith(at)example.com |
| **Address 1** | Primary street address | "123 Main Street" |
| **Address 2** | Secondary address line | "Apt 4B" |
| **Address 3** | Additional address information | "Building C" |
| **City** | City of residence | "Melbourne" |
| **State** | State or province | "Victoria" |
| **Post Code** | Postal/ZIP code | "3000" |
| **Country Code** | ISO country code | "AU" |
| **Time Zone** | Patient's time zone | "Australia/Melbourne" |
| **Emergency Contact** | Emergency contact details | "Jane Smith - 0412345678" |

### Healthcare Information

| Field | Description | Example |
|-------|-------------|---------|
| **Medicare** | Medicare number | "1234567890" |
| **Medicare Reference Number** | Medicare reference | "1" |
| **DVA Card Number** | Department of Veterans' Affairs card | "V123456" |
| **Referral Source** | How the patient found you | "Google", "Friend referral" |

### Communication Preferences

| Field | Description | Values |
|-------|-------------|--------|
| **Accepted Privacy Policy** | Has agreed to privacy policy | Yes/No |
| **Accepts Email Marketing** | Consents to marketing emails | Yes/No |
| **Accepts SMS Marketing** | Consents to SMS marketing | Yes/No |
| **Receives Confirmation Emails** | Gets appointment confirmations | Yes/No |
| **Receives Cancellation Emails** | Gets cancellation notifications | Yes/No |
| **Reminder Type** | Preferred reminder method | "Email", "SMS", "Phone" |

### System Information

| Field | Description | Purpose |
|-------|-------------|---------|
| **Created At** | When patient record was created | Track registration date |
| **Updated At** | Last time record was modified | Monitor recent changes |
| **Archived At** | When patient was archived (if applicable) | Identify inactive patients |
| **Merged At** | When patient was merged with another record | Track data consolidation |
| **Patient Created** | Date portion of creation time | Simplified date for reporting |
| **Last Interaction** | Date of most recent appointment or creation | Track patient activity |

### Administrative Fields

| Field | Description | Use Case |
|-------|-------------|----------|
| **Old Reference ID** | Previous system identifier | Migration tracking |
| **Appointment Notes** | Special scheduling instructions | "Prefers morning appointments" |
| **Notes** | General patient notes | Clinical or administrative notes |
| **Invoice Default To** | Default invoice recipient | "Patient", "Insurance" |
| **Invoice Email** | Specific email for invoices | billing(at)company.com |
| **Invoice Extra Information** | Additional invoice details | Purchase order numbers |
| **Label** | Display name for the patient | Formatted name for lists |

## Key Metrics and Calculations

### Patient Activity Measures

| Measure | What It Shows | How It's Calculated |
|---------|---------------|-------------------|
| **Count of Customer** | Total number of unique patients | Counts distinct Patient IDs |
| **Appointment Count** | Number of appointments per patient | Counts related appointments |
| **Total Invoice Sum** | Number of invoices per patient | Counts related invoices |
| **Date of Last Sale** | Most recent appointment date | Maximum start date from appointments |

### New Patient Tracking

| Measure | What It Shows | How It's Calculated |
|---------|---------------|-------------------|
| **Is New Client (3 months)** | Whether patient is new within 3 months | 1 if created within last 90 days, 0 otherwise |
| **Start Date for New** | Cutoff date for new patients | 90 days ago from today |
| **New Clients (3 months)** | Count of new patients in period | Sum of patients flagged as new |
| **PVA (Patient Value Average)** | Average appointments per new client | Total appointments ÷ New clients |

## Understanding Patient Status

### Active vs. Inactive Patients

- **Active Patients**: Have a blank "Archived At" field
- **Archived Patients**: Have a date in the "Archived At" field
- **Merged Patients**: Have a date in the "Merged At" field and reference to the primary patient record

### New Patient Identification

The system automatically identifies new patients based on:

- Registration date within the last 90 days
- First appointment scheduling
- Account creation timing

## Relationships with Other Tables

The Patients table connects to other parts of your data:

- **Appointments**: Each appointment links to one patient
- **Invoices**: Each invoice is associated with one patient
- **Date Tables**: Patient creation dates link to calendar information

## Common Use Cases

### Patient Demographics Analysis

- Age distribution of patient base
- Geographic distribution by state/city
- Gender demographics

### Patient Acquisition Tracking

- New patient registrations over time
- Referral source effectiveness
- Patient growth trends

### Patient Communication Preferences

- Marketing consent rates
- Preferred communication methods
- Contact information completeness

### Patient Activity Monitoring

- Last interaction dates
- Appointment frequency per patient
- Invoice history per patient

## Tips for Using This Data

1. **Privacy Considerations**: Always respect patient privacy when creating reports
2. **Data Quality**: Monitor for missing contact information or incomplete records
3. **Segmentation**: Use demographics and preferences to create targeted patient groups
4. **Trends**: Track new patient acquisition and existing patient retention
5. **Communication**: Respect patient communication preferences for marketing and notifications

## Frequently Asked Questions

**Q: What makes a patient "new"?**
A: A patient is considered new if they were created within the last 90 days (3 months).

**Q: What's the difference between "First Name" and "Preferred First Name"?**
A: "First Name" is the official name on file, while "Preferred First Name" is what the patient likes to be called.

**Q: Can patients have multiple addresses?**
A: The system supports up to 3 address lines for comprehensive address information.

**Q: What happens to archived patients?**
A: Archived patients are inactive but remain in the system for historical reporting purposes.

**Q: How is patient age calculated?**
A: Age is automatically calculated based on the date of birth and updates dynamically.

---

*This documentation is designed to help you understand and effectively use patient data in your Cliniko Reports. For technical questions about the data model, please refer to the technical documentation.*

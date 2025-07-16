# Invoices and Invoice Items Guide

## Overview

The Invoices and Invoice Items tables work together to provide complete billing and financial information for your Cliniko practice. The Invoices table contains the main invoice details (header information), while the Invoice Items table contains the individual line items that make up each invoice. Together, they give you detailed insights into your revenue, payment patterns, and financial performance.

## How These Tables Work Together

- **Invoices Table**: Contains one record per invoice with totals, dates, and payment status
- **Invoice Items Table**: Contains multiple records per invoice - one for each service, product, or charge on the invoice
- **Relationship**: Each invoice item belongs to exactly one invoice, but each invoice can have multiple items

## Invoices Table

### Basic Invoice Information

| Field | Description | Example |
|-------|-------------|---------|
| **Invoice ID** | Unique identifier for each invoice | "INV-2024-001" |
| **Issue Date** | When the invoice was created | "2024-03-15" |
| **Closed Date** | When the invoice was paid/closed | "2024-03-20" |
| **Status Code** | Numeric code representing payment status | "1" (paid), "0" (unpaid) |
| **Status Description** | Human-readable payment status | "Paid", "Unpaid", "Overdue" |
| **Close Time** | Days between issue and payment | "5" (days) |

### Financial Amounts

| Field | Description | Example |
|-------|-------------|---------|
| **Total Amount** | Full invoice amount including tax | "$150.00" |
| **Net Amount** | Invoice amount before tax | "$136.36" |
| **Tax Amount** | Total tax on the invoice | "$13.64" |
| **Discounted Amount** | Total discounts applied | "$10.00" |

### System References

| Field | Description | Purpose |
|-------|-------------|---------|
| **practitioner.links.self** | Link to the practitioner who created the invoice | Connect to practitioner data |
| **patient.links.self** | Link to the patient being invoiced | Connect to patient data |
| **appointment.links.self** | Link to related appointment (if applicable) | Connect to appointment data |
| **business.links.self** | Link to the business/location | Connect to business data |

## Invoice Items Table

### Basic Item Information

| Field | Description | Example |
|-------|-------------|---------|
| **Invoice Item ID** | Unique identifier for each line item | "ITEM-001" |
| **Name** | Description of the service or product | "Consultation", "Massage Therapy" |
| **Code** | Item code or SKU | "CONS-60", "MASS-30" |
| **Quantity** | Number of units | "1", "2" |

### Pricing Information

| Field | Description | Example |
|-------|-------------|---------|
| **Unit Price** | Price per unit before discounts | "$100.00" |
| **Net Price** | Price after discounts, before tax | "$90.00" |
| **Tax Amount** | Tax applied to this item | "$9.00" |
| **Total Including Tax** | Final amount for this line item | "$99.00" |

### Discount Information

| Field | Description | Example |
|-------|-------------|---------|
| **Discount Percentage** | Percentage discount applied | "10%" |
| **Discounted Amount** | Dollar amount of discount | "$10.00" |
| **Is Monetary Discount** | Whether discount is fixed amount vs percentage | Yes/No |
| **Concession Type Name** | Type of concession applied | "Senior", "Student", "Health Fund" |

### Tax Information

| Field | Description | Example |
|-------|-------------|---------|
| **Tax Name** | Name of the tax applied | "GST", "Sales Tax" |
| **Tax Rate** | Tax percentage | "10%", "8.25%" |

### Invoice Item References

| Field | Description | Purpose |
|-------|-------------|---------|
| **invoice.links.self** | Link to the parent invoice | Connect to invoice header |
| **billable_item.links.self** | Link to the billable item definition | Connect to service/product catalog |
| **product.links.self** | Link to product information | Connect to product data |

## Key Financial Metrics

### Invoice-Level Measures

| Measure | What It Shows | How It's Calculated |
|---------|---------------|-------------------|
| **TotalM** | Sum of all invoice amounts | Sum of Total Amount field |
| **Income YTD** | Year-to-date revenue | Cumulative total from start of year |
| **Income YTD LY** | Last year's YTD revenue | Same period last year comparison |
| **PVA$** | Revenue per patient | Total revenue ÷ Number of patients |

## Understanding Invoice Status

### Payment Status Codes

- **0**: Unpaid - Invoice has been issued but not paid
- **1**: Paid - Invoice has been fully paid
- **2**: Partially Paid - Some payment received but balance remaining
- **3**: Overdue - Invoice past due date without payment

### Invoice Lifecycle

1. **Created**: Invoice is generated with Issue Date
2. **Sent**: Invoice is sent to patient/payer
3. **Paid**: Payment is received and invoice is closed
4. **Overdue**: Invoice passes due date without payment

## Common Calculations

### Revenue Analysis

- **Total Revenue**: Sum of all Total Amount fields
- **Average Invoice Value**: Total revenue ÷ Number of invoices
- **Revenue by Service**: Group by Invoice Item Name
- **Tax Collected**: Sum of Tax Amount fields

### Payment Performance

- **Days to Payment**: Average Close Time for paid invoices
- **Payment Rate**: Percentage of invoices with Status = Paid
- **Outstanding Balance**: Sum of unpaid invoice amounts

### Discount Analysis

- **Total Discounts Given**: Sum of Discounted Amount
- **Discount Rate**: Discounts ÷ Gross Revenue
- **Most Common Concessions**: Group by Concession Type Name

## Relationships with Other Tables

### Invoice Connections

- **Patients**: Each invoice belongs to one patient
- **Practitioners**: Each invoice is created by one practitioner
- **Appointments**: Invoices may relate to specific appointments
- **Businesses**: Each invoice belongs to one business location

### Invoice Item Connections

- **Invoices**: Each item belongs to one invoice
- **Products**: Items may link to product catalog
- **Billable Items**: Items link to service definitions

## Common Use Cases

### Financial Reporting

- Monthly/quarterly revenue reports
- Tax reporting and GST calculations
- Payment collection performance
- Outstanding accounts receivable

### Service Analysis

- Most popular services by revenue
- Service profitability analysis
- Discount impact on revenue
- Quantity trends by service type

### Patient Billing Analysis

- Average patient invoice value
- Payment behavior patterns
- Concession usage rates
- Revenue per patient over time

### Business Performance

- Revenue by practitioner
- Revenue by location
- Seasonal revenue patterns
- Growth trends over time

## Tips for Using This Data

### Financial Analysis

1. **Use Net Amount** for pre-tax revenue calculations
2. **Monitor Close Time** to track payment collection efficiency
3. **Analyze Discount Patterns** to understand pricing strategies
4. **Track YTD Metrics** for performance monitoring

### Data Quality Checks

1. **Verify Tax Calculations**: Tax Amount should equal Net Amount × Tax Rate
2. **Check Invoice Totals**: Total Amount should equal Net Amount + Tax Amount
3. **Monitor Status Consistency**: Closed Date should exist for paid invoices
4. **Validate Quantities**: Ensure reasonable quantities for services

### Reporting Best Practices

1. **Filter by Date Range**: Use Issue Date for revenue period analysis
2. **Group by Service Type**: Use Invoice Item Name for service analysis
3. **Separate by Status**: Distinguish between paid and unpaid invoices
4. **Consider Discounts**: Report both gross and net revenue figures

## Frequently Asked Questions

**Q: Why might an invoice have multiple items?**
A: A single visit might include multiple services (consultation + treatment), or a patient might purchase multiple products in one transaction.

**Q: What's the difference between Net Amount and Total Amount?**
A: Net Amount is before tax, Total Amount includes tax. The difference is the Tax Amount.

**Q: How do I calculate the effective discount rate?**
A: Divide the Discounted Amount by the original price (Unit Price × Quantity).

**Q: Can an invoice item have no tax?**
A: Yes, some services or products may be tax-exempt, resulting in zero Tax Amount.

**Q: What does a negative Total Amount mean?**
A: This typically indicates a credit note or refund issued to the patient.

**Q: How do I find the most profitable services?**
A: Group invoice items by Name and sum the Total Including Tax, then sort by highest revenue.

**Q: What's the relationship between invoices and appointments?**
A: Not all invoices relate to appointments (product sales), but appointment-based invoices will have the appointment reference.

## Sample Calculations

### Average Invoice Value

```text
Total Revenue ÷ Number of Invoices
```

### Service Revenue Ranking

```text
Group by Invoice Item Name
Sum Total Including Tax
Order by highest revenue
```

### Monthly Revenue Growth

```text
Compare current month Total Amount to previous month
Calculate percentage increase/decrease
```

### Payment Collection Rate

```text
(Number of Paid Invoices ÷ Total Invoices) × 100
```

---

*This documentation helps you understand and effectively use invoice and billing data in your Cliniko Reports. The combination of invoice headers and line items provides comprehensive financial insights for your practice.*

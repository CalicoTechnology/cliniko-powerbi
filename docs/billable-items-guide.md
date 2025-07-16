# Billable Items Guide

## Overview

The Billable Items table contains the master catalog of all services and products that can be billed to patients. This table serves as the foundation for consistent pricing and billing across your practice. It defines what can be invoiced, standardizes pricing, and helps maintain accurate financial records.

## Basic Billable Item Information

### Item Identity

| Field | Description | Example |
|-------|-------------|---------|
| **Billable Item ID** | Unique identifier for each billable item | "BILL-001", "SERV-456" |
| **Name** | Name or description of the billable item | "Initial Consultation", "Ultrasound Therapy" |
| **Item Code** | Code or SKU for the billable item | "INIT-CONS", "ULTRA-30" |
| **Item Type** | Category classification of the item | "Service", "Product", "Procedure" |

### Pricing Information

| Field | Description | Example |
|-------|-------------|---------|
| **Price** | Standard price for the billable item | "$150.00", "$75.00", "$25.00" |

### System Information

| Field | Description | Purpose |
|-------|-------------|---------|
| **Created At** | When the billable item was added to system | Track item introduction |

## Understanding Item Types

### Service Items

Services are intangible offerings provided by practitioners:

- **Consultations**: Initial assessments, follow-ups, reviews
- **Treatments**: Physiotherapy, massage, acupuncture
- **Procedures**: Injections, minor procedures, diagnostics
- **Assessments**: Functional assessments, outcome measures

### Product Items

Products are physical items sold to patients:

- **Supplements**: Vitamins, minerals, herbal products
- **Equipment**: Exercise equipment, supports, braces
- **Supplies**: Bandages, ice packs, therapeutic items
- **Materials**: Educational materials, home care kits

### Administrative Items

Administrative items support practice operations:

- **Fees**: Cancellation fees, administrative charges
- **Deposits**: Booking deposits, treatment packages
- **Adjustments**: Discounts, credits, refunds
- **Miscellaneous**: Other billable services

## Pricing Strategy

### Standard Pricing

- **Consistent Rates**: Ensures uniform pricing across all staff
- **Transparent Billing**: Patients know what to expect
- **Simplified Invoicing**: Streamlines billing process
- **Financial Planning**: Helps with revenue forecasting

### Price Considerations

- **Market Rates**: Competitive pricing for your area
- **Cost Coverage**: Ensures profitability after expenses
- **Value Proposition**: Pricing reflects service quality
- **Patient Accessibility**: Balances profitability with affordability

## Relationships with Other Tables

### Billing and Revenue

- **Invoice Items**: Billable items appear as line items on invoices
- **Invoices**: Generated when billable items are charged
- **Patients**: Track which patients use which services
- **Practitioners**: Some items may be practitioner-specific

### Service Delivery

- **Appointments**: Many billable items relate to appointment types
- **Appointment Types**: May link to specific billable items
- **Products**: Physical products may have corresponding billable items

## Common Use Cases

### Service Catalog Management

- **Price List Maintenance**: Keep current pricing for all services
- **Service Standardization**: Ensure consistent service offerings
- **New Service Introduction**: Add new services to the catalog
- **Service Retirement**: Remove outdated services

### Financial Analysis

- **Revenue by Service**: Track income from different services
- **Popular Services**: Identify most frequently billed items
- **Pricing Analysis**: Review pricing effectiveness
- **Profitability Assessment**: Evaluate service profitability

### Billing Efficiency

- **Standardized Invoicing**: Consistent billing across all staff
- **Automated Pricing**: Reduce pricing errors
- **Quick Billing**: Streamline invoice creation
- **Audit Trail**: Track all billable services

### Operational Insights

- **Service Utilization**: Monitor which services are used most
- **Capacity Planning**: Plan resources based on service demand
- **Staff Training**: Ensure all staff know available services
- **Quality Assurance**: Maintain consistent service delivery

## Best Practices for Billable Items

### Naming Conventions

1. **Clear Names**: Use descriptive names that patients understand
2. **Consistent Format**: Follow standard naming patterns
3. **Specific Details**: Include duration or scope when relevant
4. **Professional Language**: Use appropriate medical/therapeutic terminology

### Code Management

1. **Logical Codes**: Use codes that make sense to staff
2. **Consistent Pattern**: Follow a standard coding system
3. **Avoid Duplicates**: Ensure each code is unique
4. **Regular Review**: Update codes as services change

### Pricing Management

1. **Regular Reviews**: Assess pricing at least annually
2. **Market Research**: Compare with local competitors
3. **Cost Analysis**: Ensure pricing covers all costs
4. **Documentation**: Keep records of pricing changes

## Tips for Using This Data

### Service Analysis

1. **Popular Services**: Identify most frequently billed items
2. **Revenue Contribution**: Calculate revenue by service type
3. **Pricing Effectiveness**: Monitor price changes impact
4. **Service Bundling**: Identify services commonly used together

### Financial Planning

1. **Revenue Forecasting**: Use historical data to predict future revenue
2. **Pricing Strategy**: Set optimal prices for maximum profitability
3. **Service Mix**: Balance high and low-margin services
4. **Budget Planning**: Plan expenses based on service revenue

### Operational Efficiency

1. **Billing Accuracy**: Ensure all services are properly captured
2. **Staff Training**: Keep staff current on available services
3. **System Integration**: Connect with appointment and billing systems
4. **Quality Control**: Monitor service delivery consistency

## Common Calculations

### Revenue Analysis

- **Total Revenue**: Sum of all billable item prices × quantities
- **Average Service Value**: Total revenue ÷ Number of services
- **Revenue per Service Type**: Group by item type and sum prices
- **Service Utilization Rate**: Services used ÷ Services available

### Pricing Metrics

- **Price Range**: Minimum and maximum prices in catalog
- **Average Price**: Mean price across all billable items
- **Price Distribution**: Breakdown of items by price ranges
- **Price Changes**: Track pricing adjustments over time

### Performance Indicators

- **Top Revenue Generators**: Highest revenue-producing services
- **Most Popular Services**: Most frequently billed items
- **Service Growth**: New services added over time
- **Pricing Stability**: Frequency of price changes

## Frequently Asked Questions

**Q: How often should I review billable item prices?**
A: At least annually, or when costs change significantly. Consider market conditions and inflation.

**Q: What's the difference between billable items and products?**
A: Billable items are the master catalog for billing, while products are physical inventory. They may overlap but serve different purposes.

**Q: Should I have separate items for different appointment durations?**
A: Yes, if you charge different rates for different durations (e.g., "30-min Consultation" vs. "60-min Consultation").

**Q: How do I handle service bundling?**
A: Create separate billable items for bundles, or use individual items and apply discounts during billing.

**Q: Can I change prices for existing billable items?**
A: Yes, but consider the impact on existing appointments and patient expectations. Document changes carefully.

**Q: What's the purpose of item codes?**
A: Codes provide quick reference for staff and help organize services systematically.

**Q: How do I determine appropriate pricing?**
A: Consider your costs, local market rates, value provided, and desired profit margins.

**Q: Should I include tax in the price?**
A: Typically, billable item prices are pre-tax, with tax calculated during invoicing based on local requirements.

**Q: How do I handle insurance-specific pricing?**
A: Maintain standard prices in billable items, then apply insurance-specific rates during billing.

---

*This documentation helps you effectively manage your service catalog, maintain consistent pricing, and analyze the financial performance of your billable services and products.*

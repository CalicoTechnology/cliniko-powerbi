# Products Guide

## Overview

The Products table contains comprehensive information about all physical products, supplements, and retail items available in your practice. This table manages your inventory, tracks stock levels, handles pricing, and provides insights into product sales and profitability. It's essential for practices that sell products alongside their services.

## Basic Product Information

### Product Identity

| Field | Description | Example |
|-------|-------------|---------|
| **Product Item ID** | Unique identifier for each product | "PROD-001", "SUPP-456" |
| **Name** | Product name or title | "Omega-3 Supplement", "Resistance Band" |
| **Item Code** | Product code or SKU for identification | "OM3-500", "RB-MEDIUM" |
| **Serial Number** | Unique serial number for tracking | "SN123456789" |
| **Notes** | Additional product information | "Store in cool, dry place" |

### Supplier Information

| Field | Description | Example |
|-------|-------------|---------|
| **Product Supplier Name** | Name of the supplier or manufacturer | "Health Products Inc.", "Fitness Equipment Co." |

## Inventory Management

### Stock Tracking

| Field | Description | Example |
|-------|-------------|---------|
| **Stock Level** | Current quantity available | "25", "0", "150" |
| **Current Stock** | Real-time stock for selected product | "25" (for single product view) |
| **Stock On Date** | Historical stock level on specific date | "30" (accounting for future adjustments) |

## Financial Information

### Pricing Structure

| Field | Description | Example |
|-------|-------------|---------|
| **Cost Price** | Wholesale/purchase price | "$12.50", "$8.95" |
| **Price Excluding Tax** | Retail price before tax | "$25.00", "$18.90" |
| **Price Including Tax** | Final retail price with tax | "$27.50", "$20.79" |

## System Information

### Record Management

| Field | Description | Purpose |
|-------|-------------|---------|
| **Created At** | When product was added to system | Track product introduction |
| **Updated At** | Last modification date | Monitor recent changes |
| **Archived At** | When product was discontinued | Identify inactive products |

## Key Inventory Metrics

### Stock Management Measures

| Measure | What It Shows | How It's Calculated |
|---------|---------------|-------------------|
| **Current Stock** | Stock level for selected product | Uses SELECTEDVALUE function |
| **Stock On Date** | Historical stock accounting for future changes | Current stock minus future adjustments |

## Understanding Product Status

### Product Lifecycle

1. **Active**: Product is available for sale (no archived date)
2. **Archived**: Product is discontinued but remains for historical records
3. **Out of Stock**: Product is active but stock level is zero
4. **Low Stock**: Product is below minimum stock threshold

### Stock Level Indicators

- **In Stock**: Stock level > 0
- **Out of Stock**: Stock level = 0
- **Negative Stock**: Stock level < 0 (indicates overselling)
- **Critical Stock**: Stock level below reorder point

## Pricing and Profitability

### Price Calculations

- **Markup**: (Price Excluding Tax - Cost Price) ÷ Cost Price × 100
- **Margin**: (Price Excluding Tax - Cost Price) ÷ Price Excluding Tax × 100
- **Tax Amount**: Price Including Tax - Price Excluding Tax

### Profitability Analysis

- **Gross Profit per Unit**: Price Excluding Tax - Cost Price
- **Total Stock Value**: Stock Level × Cost Price
- **Potential Revenue**: Stock Level × Price Excluding Tax

## Common Calculations

### Inventory Valuation

- **Stock Value (Cost)**: Stock Level × Cost Price
- **Stock Value (Retail)**: Stock Level × Price Excluding Tax
- **Potential Profit**: Stock Level × (Price Excluding Tax - Cost Price)

### Sales Analysis

- **Revenue per Product**: Sum of sales × Price Excluding Tax
- **Profit per Product**: Sum of sales × (Price Excluding Tax - Cost Price)
- **Inventory Turnover**: Sales quantity ÷ Average stock level

### Stock Management

- **Reorder Point**: When to reorder based on usage patterns
- **Days of Stock**: Stock Level ÷ Average daily usage
- **Stock Movement**: Track increases/decreases in stock levels

## Relationships with Other Tables

### Sales and Billing

- **Invoice Items**: Products sold appear as invoice line items
- **Invoices**: Product sales generate invoices
- **Patients**: Track which patients purchase which products

### Stock and Inventory Management

- **Stock Adjustments**: Track changes in stock levels
- **Billable Items**: Products may be linked to billable services

## Common Use Cases

### Inventory Control

- **Stock Monitoring**: Track current stock levels across all products
- **Reorder Management**: Identify products that need restocking
- **Supplier Analysis**: Evaluate supplier performance and costs
- **Product Performance**: Identify best and worst-selling products

### Financial Analysis

- **Profitability Review**: Calculate profit margins by product
- **Revenue Analysis**: Track product sales revenue
- **Cost Management**: Monitor cost price changes over time
- **Inventory Valuation**: Calculate total inventory value

### Sales Optimization

- **Product Mix**: Analyze which products sell best together
- **Pricing Strategy**: Review pricing effectiveness
- **Margin Analysis**: Identify highest-margin products
- **Slow-Moving Stock**: Identify products that need promotion

### Operational Efficiency

- **Stock Turnover**: Monitor how quickly products sell
- **Supplier Performance**: Evaluate supplier reliability
- **Storage Optimization**: Optimize stock levels to reduce carrying costs
- **Product Lifecycle**: Manage product introduction and discontinuation

## Tips for Using This Data

### Inventory Optimization

1. **Set Reorder Points**: Establish minimum stock levels for automatic reordering
2. **Monitor Fast Movers**: Keep adequate stock of popular products
3. **Identify Slow Movers**: Review products with low turnover
4. **Seasonal Adjustments**: Adjust stock levels for seasonal demand

### Profit Analysis

1. **Regular Margin Review**: Periodically review profit margins
2. **Cost Monitoring**: Track cost price changes from suppliers
3. **Pricing Strategy**: Use data to optimize pricing
4. **Product Mix**: Focus on high-margin products

### Data Quality

1. **Regular Stock Counts**: Verify system stock levels with physical counts
2. **Update Pricing**: Keep cost and retail prices current
3. **Supplier Information**: Maintain accurate supplier details
4. **Product Information**: Keep descriptions and notes up to date

## Frequently Asked Questions

**Q: What's the difference between "Cost Price" and "Price Excluding Tax"?**
A: Cost Price is what you pay the supplier, Price Excluding Tax is what you charge customers before tax.

**Q: How do I calculate profit margin?**
A: Profit Margin = (Price Excluding Tax - Cost Price) ÷ Price Excluding Tax × 100

**Q: What happens when stock level reaches zero?**
A: The product becomes unavailable for sale until stock is replenished. Consider setting reorder points above zero.

**Q: How is "Stock On Date" different from "Current Stock"?**
A: "Stock On Date" shows historical stock levels, accounting for future adjustments, while "Current Stock" shows the current quantity.

**Q: Should I archive products that are out of stock?**
A: Only archive products that are permanently discontinued. Out-of-stock products can be restocked.

**Q: How do I track which products are selling well?**
A: Look at invoice items data to see product sales volume and combine with stock turnover analysis.

**Q: What's a good profit margin for products?**
A: This varies by industry and product type. Healthcare products typically have margins between 40-60%.

**Q: How often should I update cost prices?**
A: Review cost prices whenever you receive new supplier pricing or at least quarterly to maintain accurate margins.

**Q: What's the purpose of the serial number field?**
A: Serial numbers help track individual items, especially for warranty, recalls, or high-value products.

---

*This documentation helps you effectively manage your product inventory, optimize pricing, and analyze product performance to maximize profitability and ensure adequate stock levels.*

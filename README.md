# Power BI Data Modeling Project

A Power BI data modeling project focused on transforming a complex source model into a clean, scalable **star schema** designed for reliable reporting and analysis.

## Project Overview

The project followed four phases:

1. **Prepare & Explore** – Understand the business processes, source data, and grain.
2. **Dimensions** – Identify and build reusable business context.
3. **Facts** – Model business events according to their defined grain.
4. **Polish** – Apply consistent naming, organization, and data modeling standards.

## Modeling Principles

The model was built around four rules:

- **Build a star schema**
- **Read the grain** – Clearly define what one row represents.
- **Earn its place** – Keep only data required for reporting.
- **Protect the numbers** – Design relationships to support accurate analysis.

### Standards

- Language: English
- Naming: `snake_case`
- Dimensions: `dim_`
- Facts: `fact_`
- Keys: `_key` / `_id`
- Friendly and consistent names

## Final Data Model

### Dimensions
- `dim_customer`
- `dim_product`
- `dim_order_flags`
- `dim_geo`
- `dim_campaign`

### Facts
- `fact_sales`
- `fact_inventory`
- `fact_campaign_spend`
- `fact_promotion_coverage`
- `fact_orders_process`
- `fact_sales_targets`

### Special Fact Types

- **`fact_promotion_coverage`** – A **factless fact** representing product-campaign coverage without numerical measures.
- **`fact_orders_process`** – An **accumulating snapshot** containing one row per order/process and the milestone dates throughout its lifecycle.

## Row-Level Security

A dedicated `security` table was implemented to support **Row-Level Security (RLS)**.

Each user's email is mapped to a specific region, allowing Power BI to dynamically restrict the data visible to each user based on their assigned regional access.

## Model Transformation

### Before

![Before Data Model](Documentation/data_model_before.png)

### After

![After Data Model](Documentation/data_model_after.png)

## Power Query

Power Query was used to prepare, transform, and organize the source data before building the final analytical model.

![Power Query](Documentation/power_query_structure.png)

## Key Takeaways

- Explored the business and data before modeling.
- Defined table grain before creating relationships.
- Built a star schema around business processes.
- Applied dimensional modeling principles.
- Implemented both factless and accumulating snapshot fact tables.
- Applied Row-Level Security for regional data access.
- Established consistent naming and modeling standards.

## Tools

**Power BI | Power Query | DAX | Data Modeling | Star Schema | Row-Level Security**

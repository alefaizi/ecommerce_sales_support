# Sales & Support Dashboard — Power BI & Looker Studio

> Performance analysis of sales and customer support for a digital products company (online courses, e-books, and mentoring programs).

---

## Overview

This project is an interactive dashboard developed in **Power BI** and replicated in **Looker Studio**, designed to consolidate sales and support metrics into a single management view. Data was provided as `.csv` files and connected directly to the visualization tools — no external code transformations required.

The project demonstrates that mastering the core concepts of data visualization and modeling makes migrating between different tools a natural process: the entire dashboard was successfully replicated in Looker Studio.

---

## Dashboard Pages

### 1. Sales Overview

Tracks commercial performance throughout 2024:

| Metric | Value |
|---|---|
| Total Revenue | BRL 1.96M |
| Revenue Target | BRL 2.5M |
| Average Ticket | BRL 653.42 |
| Total Purchases | 3,000 |
| Total Users | 1,200 |
| Average Customer Income | BRL 8,364.49 |
| Average Customer Age | 38 years |

**Product Mix:**
- Mentoring: 34.73%
- E-book: 33.13%
- Course: 32.13%

**Payment Methods:**
- Bank Slip (Boleto): 50.60%
- Credit Card: 49.40%

Also includes: monthly trend of total revenue vs. average ticket, income distribution by state (Brazil map), and new customers per month.

---

### 2. Support Overview

Tracks customer support team performance:

| Metric | Value |
|---|---|
| Average Resolution Time | 4 days |
| Average NPS | 5.4 |
| Total Tickets | 1,564 |

**Ticket Distribution by Type:**
- Cancellation: 397
- Access Issue: 397
- Product Question: 389
- Password Recovery: 381

**Ticket Status:**
- Resolved: 33.56%
- In Progress: 35.16%
- Open: 31.28%

Also includes: agent ranking by average NPS and resolution time, average handling time by ticket type over the year, and an open/in-progress ticket control panel.

---

## Data Model

The model follows a star schema with four connected tables:

```
Calendar ──┬── purchases ── users
           └── zendesk_api
```

| Table | Description |
|---|---|
| `purchases` | Sales transactions: product type, payment method, amount, status, dates |
| `users` | Customer profiles: location, income, age, registration date |
| `zendesk_api` | Support tickets: type, agent, NPS, resolution time, status |
| `Calendar` | Date table for time intelligence (month, year, quarter, etc.) |

---

## Tools Used

- **Power BI Desktop** — primary dashboard development
- **Looker Studio** — dashboard replication
- **CSV** — data source connected directly to both tools

---

## Project Highlights

- **Cross-platform portability:** the same dashboard was delivered in both Power BI and Looker Studio, demonstrating that modeling and visualization concepts transfer across platforms.
- **360° view:** combining commercial and support metrics in a single panel enables identifying correlations between sales performance and customer satisfaction.
- **Star schema modeling:** a dedicated calendar table enables precise time series analysis across all dimensions.
- **Product segmentation:** analysis by product type (course, e-book, mentoring) across both volume and revenue generated.

---

## Repository Structure

```
├── data/
│   ├── purchases.csv
│   ├── users.csv
│   └── zendesk_api.csv
├── powerbi/
│   └── dashboard.pbix
├── screenshots/
│   ├── sales_overview.png
│   └── support_overview.png
└── README.md
```

---

## How to Reproduce

1. Clone the repository.
2. Open the `.pbix` file in Power BI Desktop.
3. Update the data source paths to the local directory where the `.csv` files are saved.
4. Click **Refresh** to load the data.

For Looker Studio, import the `.csv` files as data sources and recreate the table connections according to the data model described above.

To access the dashboard in Looker Studio, [click here](https://datastudio.google.com/s/uR6-WI0revQ
)

---

## Dashboard Preview

**Sales Overview**

![First Page](/screenshots/sales_overview.png)

**Support Overview**

![Second Page](/screenshots/support_overview.png)
# YottaFlex Inventory Intelligence — Assumptions and Design Decisions

## 1. Project Scope

This project is a proof of concept for demand forecasting and inventory replenishment across multiple stores and SKUs.

The goal is to demonstrate an executable workflow that generates data, forecasts demand, identifies inventory risks, and produces replenishment recommendations.

It is not intended to be a production-ready inventory management system.

## 2. Data Assumptions

- The project uses synthetic data rather than real customer or retailer data.
- The configured scenario includes 50 SKUs, 5 stores, and 10 suppliers.
- Historical data covers 90 days, beginning January 1, 2026.
- A fixed random seed supports reproducible data generation.
- Synthetic demand is treated as an approximation of real-world purchasing behavior, not as evidence of actual customer demand.
- Inventory stockouts can cause observed sales to understate underlying demand.

## 3. Forecasting Assumptions

- The forecast horizon is 14 days.
- Forecasting uses a baseline approach suitable for an explainable proof of concept.
- Forecast accuracy is evaluated using metrics including WAPE, MAE, RMSE, and bias.
- Results on synthetic data do not establish accuracy on real-world operational data.
- Forecast quality may deteriorate when customer behavior, promotions, seasonality, or supply conditions change.

## 4. Replenishment Assumptions

- The target service level is 95%.
- The inventory review period is 7 days.
- Replenishment decisions use forecast demand, inventory position, and supplier lead-time information.
- Recommendations are decision-support outputs, not automatically approved purchase orders.
- Operational constraints such as supplier capacity, warehouse space, and purchasing budgets may require additional review.

## 5. Design Decisions and Trade-offs

- **Synthetic data:** Enables an executable and reproducible demonstration without access to confidential operational data, but limits real-world validity.
- **Baseline forecasting:** Prioritizes transparency and ease of validation over complex model sophistication.
- **DuckDB:** Provides a lightweight analytical database appropriate for a local proof of concept.
- **Streamlit:** Enables rapid development of an interactive inventory dashboard.
- **FastAPI:** Exposes forecasts and recommendations programmatically.
- **Docker:** Provides a more consistent way to run the application across environments.

## 6. Testing and Validation

The project includes automated tests covering data integrity, forecasting, replenishment, and reproducibility.

During development, the test suite passed 27 tests. The dashboard, API, and Docker workflow were also exercised locally.

A fresh-clone setup test remains an important final verification before submission.

## 7. Known Limitations

- Synthetic data may not reflect actual retail operations.
- The forecasting approach is a baseline rather than a fully optimized production model.
- The application does not integrate with live ERP, POS, or supplier systems.
- Replenishment recommendations require business review before execution.
- Security, authentication, monitoring, and production deployment controls would require additional work.

## 8. Future Improvements

Potential improvements include evaluating more sophisticated forecasting models, incorporating promotional calendars, connecting real operational data, adding supplier constraints, and monitoring forecast performance over time.

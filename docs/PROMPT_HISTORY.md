# AI Prompt History — YottaFlex Inventory Intelligence

## AI Tool

ChatGPT (OpenAI)

## Development Interaction Summary

The following summarizes the main topics covered in my ChatGPT-assisted development conversation. This is a thematic summary, not a verbatim transcript of every prompt.

| Stage | Prompt topic | AI assistance |
|---|---|---|
| 1. Project planning | Understanding the inventory intelligence challenge and implementation requirements | Helped break the project into executable steps |
| 2. Synthetic data | Generating SKU, store, supplier, sales, and inventory datasets | Assisted with data generation and validation |
| 3. Forecasting | Implementing demand forecasting and measuring accuracy | Suggested forecasting logic and evaluation metrics |
| 4. Replenishment | Calculating inventory risks and purchase recommendations | Assisted with replenishment logic and tests |
| 5. Dashboard | Building an interactive Streamlit dashboard | Helped implement and debug dashboard components |
| 6. API | Exposing forecasts and recommendations using FastAPI | Assisted with endpoints and local testing |
| 7. Testing | Validating data integrity, forecasts, and reproducibility | Helped create tests and troubleshoot failures |
| 8. Deployment | Running the application using Docker | Assisted with container setup and troubleshooting |
| 9. Documentation | Preparing README, assumptions, and AI disclosure | Helped draft and organize documentation |
| 10. GitHub | Preparing a public repository for submission | Assisted with Git commands and authentication troubleshooting |

## Human Review and Validation

I ran the application locally, executed the automated test suite, checked dashboard and API behavior, and tested Docker execution.

The automated test suite passed 27 tests during development.

## Disclosure

ChatGPT was used substantially for implementation guidance, debugging, and documentation. The summary above does not replace the original conversation transcript.

The original prompts should be supplied separately or appended as a redacted transcript to satisfy the challenge's explicit prompt-history requirement.

No passwords, access tokens, or private credentials should be included in the submitted materials.

## Selected Verbatim User Prompts From Development Verification

The following are actual user messages from the ChatGPT conversation,
preserved as examples of AI-assisted debugging and verification.
This is a selected excerpt, not the complete conversation history.

### Prompt 1 — Fresh-clone data generation failure

```text
python -m src.generate_data

Generating YottaFlex master data...
Generating supplier-SKU relationships...
Generating 90 days of daily demand...
Simulating inventory and stockouts...
Generating supplier lead-time observations...

_duckdb.CatalogException: Catalog Error:
Table with name SalesHistory does not exist!

Prompt 2 — Forecast output directory failure
python -m src.forecast

Loading sales history...
Generating demand forecasts...

OSError: Cannot save file into a non-existent directory:
'outputs/forecasts'


Prompt 3 — Forecasting verification
python -m src.forecast

Forecast rows: 3500
Forecast saved to: outputs/forecasts/baseline_forecast.csv

Prompt 4 — Automated testing
27 passed in 10.95s

Prompt 5 — Git whitespace verification
git diff --check
src/forecast.py:91: trailing whitespace.
src/forecast.py:95: trailing whitespace.
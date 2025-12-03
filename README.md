## FX-Consolidation-Dashboard

A specialised financial dashboard simulating multi-entity consolidation and foreign exchange translation (IAS 21)

# The Architecture

This tool bridges the gap between raw ledger data and reported financials. It demonstrates how modern web technologies can automate the "Month End" translation process that is typically handled manually in Excel or via expensive ERP modules.

# Core Functions

  - Data Ingestion: Simulates a JSON payload from a US Subsidiary ledger (Trial Balance).

  - API Integration: Connects to ExchangeRate-API to fetch real-time USD/GBP spot rates.

  - Translation Logic: Dynamically recalculates the Consolidated P&L based on the active rate.

  - Sensitivity Analysis: Allows the user to override live rates to test variance impact against budget assumptions.

# Tech Stack

  - Core: Vanilla JavaScript.

  - Styling: Tailwind CSS.

  - Visualisation: Chart.js.

  - API: fetch().

# How to Run

This is a zero-dependency, "No-Build" application.

# Clone the repository.

  - Open index.html in any modern browser.

  - Optional: To deploy, simply enable GitHub Pages on the repository settings (Source: Main Branch).

# Finance Logic (IAS 21)

The system treats the mock data as a foreign operation (USD). It translates Revenue and Opex at the Spot Rate (simulating the weighted average rate for the period) to derive the Reporting Currency (GBP) figures.

  - USD_Balance * Active_Rate = GBP_Consolidated

  - Variance = GBP_Actuals - (USD_Actuals * Budget_Rate)

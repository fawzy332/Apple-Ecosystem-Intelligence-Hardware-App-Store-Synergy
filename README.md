Apple Ecosystem Intelligence: Hardware & App Store Synergy

An executive Power BI analytics suite designed with a minimalist "Cupertino Executive" Bento Grid aesthetic to bridge physical retail hardware performance with digital App Store ecosystem health.

🎯 Business Problem & Objective

Hardware retail sales and App Store developer metrics are traditionally analyzed in separate silos, leaving corporate strategy and platform architecture teams without a unified view of how device adoption and software evolution impact one another.

This project consolidates global device transactions (8 Regions, 43 Products, 23K Units Sold) and App Store catalog telemetry (1M+ Apps, 509K Developers, 1B+ User Reviews) into a single, decision-ready interactive report to answer:

How do hardware revenue and unit momentum align with developer release and update velocity?

Which retail channels, payment methods, demographics, and product categories drive revenue—and where are return rates spiking?

Which App Store genres represent high-rating, low-saturation growth opportunities?

Where do growing app file sizes and iOS version requirements create friction against entry-tier device storage capacities?

🏗️ Data Architecture & Modeling

The semantic model is built on a Galaxy Schema (Fact Constellation) that isolates independent business processes while synchronizing them over time:

Fact Tables:

Sale_Fact_Table: Transactional retail hardware sales, unit quantities, revenue, returns, channels, and payment methods.

App_Fact_Table: App Store catalog records, file sizes (MB), pricing models, user ratings, review volumes, required iOS versions, and release/update dates.

Conformed & Domain Dimensions:

Date_Dimension: Shared calendar table connected to both fact tables via DateKey for synchronized YoY and seasonal analysis.

Geography_Dimension, Product_Dimension, Customer_Dimension (Hardware Retail context).

Genre_Dimension, Developer_Dimension (App Store context).

🧮 Key DAX Logic & Engineering Highlights

Active App Maintenance Tracking: Strips time components from release and update timestamps (INT([Updated]) <> INT([Released])) to accurately isolate post-launch maintained software (948K active apps) without false positives from same-day ingestion.

Dynamic iOS Version String Parsing: Extracts major version integers from multi-part text strings (e.g., "17.4.1") using VALUE(LEFT(..., SEARCH(".", ...) - 1)) to evaluate compatibility thresholds numerically rather than alphabetically.

Review-Weighted Quality Scoring: Weights app star ratings by user review volume to prevent low-sample listings from distorting genre and developer rankings.

Context-Preserving Share Metrics: Uses CALCULATE and ALL modifiers to benchmark top publisher review concentration against the unfiltered ecosystem total.

📊 Report Structure (5 Pages)

Landing Page (Ecosystem Intelligence): Split-screen Bento portal pairing dual logo-anchored KPI summary strips (Hardware & Retail and App Store & Software) with four direct visual navigation cards.

Executive Overview: Top-line revenue, units sold, and YoY growth KPIs; Ecosystem Momentum combo chart overlaying monthly app releases/updates against hardware revenue; and geographic distribution via a dark-mode Azure Map.

Retail Performance: Revenue and return-rate diagnostics broken down by Sales Channel, Age Group, Product Category, Payment Method matrix, and Device Storage Size.

Market Dynamics: App catalog scale, free-app share (91.63%), and active-app velocity paired with genre review rankings, rating trends, and the Genre Opportunity Matrix scatter plot.

Ecosystem Synergy: Cross-cutting architecture analysis comparing Average App Size by Genre and Total Units Sold by Storage (exposing 64 GB entry-tier storage pressure), iOS requirement thresholds, and the Top Ecosystem Developers leaderboard.

🎨 Design System

Canvas Base: #F5F5F7 (Apple Soft Off-White)

Visual Containers: #1D1D1F (Charcoal Bento Cards)

Primary Accents: #0071E3 / #0A84FF (Apple Blue) & #64D2FF (Electric Cyan)

Typography: Segoe UI with strict Title Case hierarchy and high-contrast light-on-dark readability.

🚀 How to Use

Open the .pbix file in Power BI Desktop (latest version recommended for Azure Maps and custom shape/button states).

Start on the Landing tab for a global snapshot and click any of the four hardware-themed cards on the right to jump to that analytical module.

Use the top navigation bar on any analytical page to switch views or click the Apple logo in the top-left corner to return home.

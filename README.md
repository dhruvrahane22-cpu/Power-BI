Audio DNA: Predictive Spotify Analytics
Overview
Audio DNA is an advanced Business Intelligence application built in Power BI. Developed as a comprehensive Master of Science in Data Science academic project, its primary objective is to mathematically predict a track's commercial success probability based entirely on its raw acoustic features (e.g., Danceability, Energy, Acousticness).

Instead of relying on industry intuition, this dashboard utilizes a massive historical dataset and a custom-built Logistic Regression algorithm natively coded in DAX to run real-time predictive simulations.

The Data Architecture
A predictive model is only as robust as its underlying data. This project utilizes a highly structured, rigorously cleaned dataset:

Scale & Balance: The model is trained on a foundation of over 40,000 Spotify tracks. Crucially, the target variable is perfectly balanced (exactly 20,000 "Hits" and 20,000 "Flops"), effectively eliminating machine learning classification bias.

Modern Benchmarking: It integrates historical data (1960s–2010s) with verified modern benchmarks (2025 Top 50 & All-Time Top 100) to prove shifting consumer trends.

Data Modeling: The underlying architecture utilizes a highly optimized Star Schema, isolating descriptive metadata into Dimension tables to ensure the central Fact table processes calculations in milliseconds.

Dashboard Capabilities
The application is divided into two primary interfaces:

1. The Predictive Simulator (Page 1)
This page serves as the interactive machine learning engine.

What-If Parameters: Disconnected tables allow users to manually adjust sliders for Danceability, Instrumentalness, and Acousticness.

Live Probability Engine: As slider values change, a custom DAX formula harvests the inputs, applies Python-derived ML weights, calculates the log-odds (Z), and applies a Sigmoid Activation Function to output a real-time Hit Probability on the gauge visual.

Historical Matrix: Provides a rapid, drillable overview of average danceability and hit rates across distinct musical eras.

2. Exploratory Data Analysis (Page 2)
This interface provides the mathematical proof validating the predictive model's logic.

Trend Analysis (Combo Chart): A dual-axis time-series chart mapping the Average Danceability (columns) against Average Energy (line) across decades, visually proving the strong historical correlation between the two features.

Track Profile Comparison: Instantly visualizes the acoustic DNA of successful vs. unsuccessful tracks based on user slicer inputs.

Verifiable Data Lineage: A custom drill-down matrix utilizing DAX text substitution (SUBSTITUTE) to convert raw database URIs into live, clickable Spotify web URLs, allowing stakeholders to instantly audit and listen to the data source.

Technical Stack
Environment: Power BI Desktop

Data Transformation: Power Query (M Code) for deduplication, merging, and strict data type enforcement.

Data Modeling: Normalized Star Schema (1-to-Many, single-direction relationships).

Advanced DAX: Implementation of GENERATESERIES for variable harvesting, DIVIDE(1, 1 + EXP(-Z)) for predictive scaling, and heavy utilization of variables (VAR) for code readability and performance.

# COVID-19 Global Impact Analysis

## Project Overview
A comprehensive analysis of the COVID-19 pandemic from 2020-2025, examining global patterns, drivers of outcomes, and vaccination impact. This project transforms raw pandemic data into actionable insights through careful data modeling and visualization.

---

## Project Structure
```
covid-analysis/
├── data/                   # Raw and processed data files
├── sql/                    # PostgreSQL queries and views
├── powerbi/                # Dashboard files
└── docs/                   # Documentation
```

---

## Data Pipeline

### Data Sources
- **Primary Dataset**: Our World in Data COVID-19 Dataset
- **Time Period**: 2020-2025
- **Initial Size**: 60+ columns across 242 countries

### Data Cleaning & Transformation
**Field Rationalization:**
- Reduced dataset from 60+ to 30 focused columns
- Prioritized per-capita metrics for fair country comparisons
- Used smoothed (7-day average) data to identify true trends
- Eliminated redundant and low-quality metrics

**Key Decisions:**
- Used `_per_million` metrics over raw counts
- Kept `_smoothed` versions for trend analysis
- Maintained demographic fields for correlation analysis
- Excluded metrics with significant data quality issues

### Data Model
**Core COVID Metrics:**
- Cases: `total_cases`, `new_cases_smoothed`, `total_cases_per_million`
- Deaths: `total_deaths`, `new_deaths_smoothed`, `total_deaths_per_million`
- Healthcare: `hosp_patients_per_million`, `icu_patients_per_million`

**Vaccination Tracking:**
- Coverage: `people_vaccinated_per_hundred`, `people_fully_vaccinated_per_hundred`
- Boosters: `total_boosters_per_hundred`
- Rollout: `new_vaccinations_smoothed`

**Country Characteristics:**
- Economic: `gdp_per_capita`, `human_development_index`
- Healthcare: `hospital_beds_per_thousand`, `life_expectancy`
- Demographic: `median_age`, `population_density`

---

## Analysis Framework

### Business Questions
1. **Global Impact**: How did COVID-19 distribute across regions and over time?
2. **Drivers Analysis**: What factors correlated with better/worse outcomes?
3. **Intervention Effectiveness**: How did vaccinations and policies impact the pandemic?

### Methodology
- **Comparative Analysis**: Country-to-country and region-to-region comparisons
- **Correlation Analysis**: Relationships between socioeconomic factors and outcomes
- **Trend Analysis**: Pandemic evolution over 5-year period
- **Policy Evaluation**: Effectiveness of government responses

---

## Technical Implementation

### Database Schema
**PostgreSQL Tables:**
- `covid_data` - Main fact table with daily country-level data
- `country_dim` - Country characteristics and metadata
- `date_dim` - Time intelligence and date hierarchy

**Key Views:**
- `global_overview` - Worldwide aggregates and trends
- `country_snapshot` - Latest metrics per country
- `continent_analysis` - Regional-level summaries

### Power BI Architecture
**Data Model:**
- Star schema with proper relationships
- Date table for time intelligence
- Consistent formatting and measure definitions

**Dashboard Pages:**
1. **Executive Overview** - High-level global impact
2. **Drivers & Correlations** - Root cause analysis
3. **Vaccination Impact** - Intervention effectiveness

---

## Key Insights

### Data Quality Findings
- Testing data completeness drops after June 2022
- Excess mortality data limited to developed nations
- Policy data availability correlates with country development level
- Smoothing essential for identifying true trends vs. reporting noise

### Analytical Challenges
- Source transition from JHU to WHO in March 2023
- Varying reporting standards across countries
- Missing data patterns requiring careful handling
- Scale differences requiring per-capita normalization

---

## Tools & Technologies

- **Database**: PostgreSQL
- **ETL**: SQL, Power Query
- **Visualization**: Power BI
- **Version Control**: Git
- **Documentation**: Markdown

---

## Project Status

### Completed
- ✅ Data sourcing and initial assessment
- ✅ Comprehensive data cleaning and rationalization
- ✅ Database schema design
- ✅ Field selection and metric validation

### In Progress
- 🔄 PostgreSQL database setup
- 🔄 SQL view development
- 🔄 Power BI data model construction

### Next Steps
- Power BI dashboard development
- Advanced correlation analysis
- Documentation finalization
- Portfolio presentation preparation

---

## Files & Assets

### Data Files
- `raw/owid-covid-data.csv` - Original dataset
- `processed/covid_analysis_clean.csv` - Cleaned dataset

### SQL Files
- `schema/setup.sql` - Database schema
- `views/analysis_views.sql` - Analytical views
- `queries/validation.sql` - Data quality checks

### Documentation
- `README.md` - Project overview (this file)
- `data_dictionary.md` - Field definitions and sources
- `methodology.md` - Analytical approach

---

## Contact

**Analyst**: [Your Name]  
**Last Updated**: [Current Date]  
**Data Version**: Our World in Data COVID-19 Dataset (2020-2025)

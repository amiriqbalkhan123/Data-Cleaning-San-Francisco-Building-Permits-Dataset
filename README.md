Phase 1: Semantic Normalization 
Description

Semantic normalization focused on improving the interpretability and consistency of categorical variables across the dataset.

Actions Performed

Converted numeric permit type codes into human-readable categorical labels (e.g., 1 → One, 2 → Two).

Standardized text-based categorical columns using title case formatting to eliminate capitalization inconsistencies.

Normalized street suffix values by mapping abbreviations and full forms to a consistent representation (e.g., Street → St, Avenue → Av).

Purpose

To ensure that categorical data is:

Human-readable

Consistent across records

Suitable for grouping, filtering, and visualization

Phase 2: Structural Cleaning
Description

Structural cleaning aimed to reduce dataset complexity by removing columns that contributed little analytical value or contained excessive missing data.

Actions Performed

Dropped low-information and high-null columns such as administrative flags and rarely populated indicators.

Removed columns not relevant to analytical objectives (e.g., unit-level identifiers that did not affect analysis).

Reduced dimensionality from approximately 45 columns to 33 carefully selected features.

Purpose

To:

Reduce noise

Improve computational efficiency

Focus analysis on meaningful attributes

Phase 3: Logical Imputation 
Description

Instead of arbitrary value imputation, domain-informed logic was used to preserve records while maintaining data integrity.

Actions Performed

Filled missing Proposed Use values using corresponding Existing Use values when applicable.

Filled missing Estimated Cost values using Revised Cost values.

Synchronized Existing Units and Proposed Units to fill gaps where one value was present.

Purpose

To:

Preserve as many records as possible

Avoid fabricating new data

Maintain logical relationships between related fields

Phase 4: Quality Filtering 
Description

Rows that failed to meet minimum quality thresholds were removed to ensure analytical reliability.

Criteria for Removal

Records were dropped if they contained missing values in:

Core geographic identifiers (e.g., Supervisor District, Zipcode, Neighborhood Boundaries)

Essential construction metadata

Critical financial attributes required for cost analysis

Purpose

To ensure that retained records are:

Analytically complete

Reliable for aggregation and modeling

Suitable for geographic and financial insights

Phase 5: Type Enforcement 
Description

Data types were explicitly enforced after cleaning to guarantee consistency and downstream compatibility.

Actions Performed

Converted numerical fields such as costs, unit counts, story counts, and plansets to integer types.

Ensured categorical and textual columns retained appropriate string formats.

Purpose

To:

Prevent implicit type errors

Improve performance

Prepare the dataset for modeling, SQL ingestion, and BI tools

Phase 6: Final Validation 
Description

A final validation step was performed to confirm the integrity of the cleaned dataset.

Actions Performed

Computed null-value ratios to ensure missing values were reduced to negligible levels.

Compared existing and proposed construction type descriptions to assess semantic consistency.

Exported the finalized dataset in CSV format for reuse.

Purpose

To ensure:

Trustworthiness of the dataset

Transparency of cleaning outcomes

Readiness for exploratory analysis, dashboards, and predictive modeling

Final Outcome

Rows reduced from ~198,600 to approximately 143,000 high-quality records

Columns reduced to 33 analytically relevant features

Missing values minimized without compromising logical consistency

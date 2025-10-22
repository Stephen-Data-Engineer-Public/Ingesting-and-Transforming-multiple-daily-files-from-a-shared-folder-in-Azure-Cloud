# Tech Stack and Architecture Decisions!

**1. Azure Data Factory**


Why this combination works best:

- Azure Data Factory Self-Hosted Integration Runtime (SHIR) handles on-prem connectivity without exposing data publicly.
- Azure Data Factory Azure Integration Runtime handles scalable, managed transformations in the cloud.
- Optimizes cost and performance: SHIR avoids unnecessary Azure runtime charges for moving on-prem data.

**
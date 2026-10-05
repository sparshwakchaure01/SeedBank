# SeedBank AI

> **Spotify recommendations, but for the seed variety that survives your changing climate.**

**PCCOE International Grand Challenge 2026**
**Theme:** AI for Climate Change
**Domain:** AgriTech & Water Resilience

---

## 1. Overview

**SeedBank AI** is an AI-powered web platform that helps farmers choose seed varieties based on their **local climate conditions, future climate trajectory, crop requirements, seed characteristics, and real farmer outcomes**.

Traditional agricultural advice often recommends seeds based on historical performance or broad regional conditions. But climate conditions are changing.

A seed that worked well in a region 10 years ago may not be the best choice for the climate farmers will experience in the coming years.

SeedBank AI addresses this by combining climate intelligence with seed data and farmer-generated outcomes to provide **personalised, explainable seed recommendations**.

### Core Idea

```text
Historical Seed Selection
          ↓
       SeedBank AI
          ↓
Climate + Seed Data + Farmer Outcomes
          ↓
Personalised Recommendations
          ↓
Better Climate-Resilient Seed Selection
```

---

# 2. Problem Statement

Farmers often select seeds using:

* Traditional knowledge
* Historical crop performance
* Generic agricultural recommendations
* Local availability
* Recommendations from suppliers or other farmers

However, climate conditions are changing due to:

* Increasing temperatures
* Irregular rainfall
* Drought conditions
* Changing growing seasons
* Water scarcity
* Increasing climate-related crop stress

This creates a major problem:

> **Farmers may continue using seed varieties that were suitable for historical climate conditions but may be less suitable for the climate their region is moving towards.**

### Existing Gap

Most agricultural advisory systems provide general recommendations.

They may consider:

* Crop
* Soil
* Season
* Current weather

But they generally do not combine all of the following into one personalised recommendation system:

```text
Future Climate Trajectory
          +
Seed Characteristics
          +
Crop Requirements
          +
Local Conditions
          +
Real Farmer Outcomes
          +
AI Recommendation
```

---

# 3. Our Solution

SeedBank AI works as a **personalised seed recommendation platform**.

A farmer provides information such as:

* Location
* Crop
* Soil type
* Water availability
* Growing conditions

The system then analyses:

* Climate conditions
* Expected climate trajectory
* Seed characteristics
* Crop requirements
* Seed resistance
* Farmer reviews
* Outcomes from farmers in similar conditions

The AI recommendation engine ranks suitable seed varieties.

### Example

```text
Farmer Input

Location: Ahmednagar
Crop: Soybean
Soil: Black Soil
Water: Limited

          ↓

SeedBank AI

Climate Analysis
+
Seed Database
+
Knowledge Graph
+
Farmer Outcomes
+
Recommendation Algorithm

          ↓

Results

Seed A → 92% Suitability
Seed B → 87% Suitability
Seed C → 81% Suitability
```

These scores are **prototype/demo outputs**, not real-world validated percentages.

---

# 4. Key Features

## 🌱 Personalised Seed Recommendations

The system recommends seed varieties according to the farmer's specific conditions.

## 🌡️ Climate-Aware Recommendations

Recommendations consider both current conditions and the expected direction of climate change.

## 🧠 AI Recommendation Engine

The system uses recommendation and similarity-based techniques to rank seed varieties.

## 🔗 Knowledge Graph

Connects relationships between:

```text
Seed
 ↓
Crop
 ↓
Climate
 ↓
Location
 ↓
Soil
 ↓
Water
 ↓
Farmer Outcomes
```

## 👨‍🌾 Farmer Reviews

Farmers can submit:

* Seed used
* Location
* Rating
* Yield/outcome
* Observations

This information becomes another input for future recommendations.

## 💡 Explainable Recommendations

Instead of simply saying:

> "Use Seed A"

the system explains:

> "Seed A is recommended because it has stronger heat tolerance, performs under lower rainfall conditions and has shown positive outcomes in climatically similar regions."

## 🔄 Continuous Data Loop

```text
Data
 ↓
Recommendation
 ↓
Farmer Uses Seed
 ↓
Farmer Submits Outcome
 ↓
New Data
 ↓
Improved Knowledge Base
 ↓
Better Recommendations
```

---

# 5. Website Structure

```text
SeedBank AI
│
├── Home
│
├── Recommendation Dashboard
│
├── Climate Dashboard
│
├── Seed Library
│
├── Farmer Reviews
│
├── Submit Crop Result
│
├── About
│
└── Admin Dashboard (Optional)
```

---

# 6. Recommendation Dashboard

This is the main feature of the platform.

### Farmer Input

```text
Location
Crop
Soil Type
Water Availability
```

### System Processing

```text
Climate Data
       +
Seed Data
       +
Knowledge Graph
       +
Farmer Outcomes
       ↓
AI Recommendation Engine
```

### Output

Each recommended seed can display:

* Seed name
* Crop
* Suitability score
* Climate compatibility
* Water requirement
* Heat resistance
* Disease resistance
* Expected suitability
* Recommendation reason
* Relevant farmer reviews

---

# 7. System Architecture

```text
                    FARMER
                       │
                       ▼
              ┌─────────────────┐
              │    FRONTEND     │
              │ React + Tailwind│
              └────────┬────────┘
                       │
                    REST API
                       │
                       ▼
              ┌─────────────────┐
              │     BACKEND     │
              │     FastAPI     │
              └───────┬─────────┘
                      │
          ┌───────────┼───────────┐
          │           │           │
          ▼           ▼           ▼
     Database    Knowledge    AI Engine
                    Graph
          │           │           │
          └───────────┼───────────┘
                      │
                      ▼
             Recommendation
                      │
                      ▼
              Farmer Dashboard
```

---

# 8. Data Sources

For the hackathon prototype, the system can initially use **structured/mock datasets**.

### Seed Data

```text
Seed ID
Seed Name
Crop
Temperature Range
Rainfall Range
Soil Type
Water Requirement
Heat Resistance
Disease Resistance
Yield Score
```

### Climate Data

```text
Location
Average Temperature
Rainfall
Temperature Trend
Rainfall Trend
Drought Index
Future Climate Indicator
```

### Farmer Reviews

```text
Review ID
Seed ID
Location
Crop
Rating
Yield/Outcome
Comment
```

### Future Real Data Sources

The prototype can later integrate:

* Weather APIs
* Climate datasets
* Government agricultural datasets
* Soil datasets
* Agricultural research databases
* Seed company datasets
* Satellite/environmental datasets

---

# 9. Database Structure

### Users

```text
id
name
state
district
```

### Seeds

```text
seed_id
seed_name
crop
temperature_range
rainfall_range
soil_type
water_requirement
heat_resistance
disease_resistance
yield_score
```

### Climate

```text
district
avg_temperature
rainfall
temperature_trend
rainfall_trend
drought_index
future_prediction
```

### Reviews

```text
review_id
seed_id
farmer
district
rating
yield
comment
```

---

# 10. Knowledge Graph

The knowledge graph represents relationships between agricultural entities.

Example:

```text
Seed A
 │
 ├── belongs to → Soybean
 │
 ├── suitable for → Black Soil
 │
 ├── tolerates → High Temperature
 │
 ├── requires → Low Water
 │
 ├── performs in → Ahmednagar
 │
 └── reviewed by → Farmer Group A
```

This allows SeedBank AI to connect information from different datasets instead of treating every data point independently.

---

# 11. AI Recommendation Engine

The recommendation engine combines multiple signals.

### Main inputs

```text
Climate Suitability
+
Seed Characteristics
+
Crop Compatibility
+
Soil Compatibility
+
Water Requirements
+
Farmer Outcomes
+
Similar Locations
```

The system calculates a suitability/ranking score and returns the top-performing candidates.

### Simplified Logic

```text
User Input
    ↓
Find Compatible Seeds
    ↓
Check Climate Compatibility
    ↓
Check Soil & Water Compatibility
    ↓
Compare Farmer Outcomes
    ↓
Calculate Similarity
    ↓
Rank Seeds
    ↓
Return Top Recommendations
```

---

# 12. Collaborative Filtering

Farmer reviews create a collaborative recommendation layer.

For example:

```text
Farmer A
Location X
Crop: Soybean
Seed A → Good Result

Farmer B
Location Y
Crop: Soybean
Similar Climate
Seed A → Good Result

New Farmer
Location Z
Similar Climate

        ↓

Seed A receives a stronger recommendation
```

The system can identify farmers/locations with similar conditions and use their outcomes as an additional recommendation signal.

---

# 13. Knowledge Graph + AI

The main innovation is not using only one technique.

SeedBank AI combines:

```text
Knowledge Graph
       +
Climate Information
       +
Seed Characteristics
       +
Collaborative Filtering
       +
Farmer Outcomes
       ↓
Personalised Recommendation
```

This creates a more context-aware recommendation system.

---

# 14. API Structure

The backend can expose REST APIs such as:

### Get Recommendations

```http
POST /api/recommend
```

Input:

```json
{
  "location": "Ahmednagar",
  "crop": "Soybean",
  "soil": "Black Soil",
  "water": "Limited"
}
```

Output:

```json
{
  "recommendations": [
    {
      "seed": "Seed A",
      "score": 92,
      "reason": "High heat tolerance and suitable for limited water conditions"
    }
  ]
}
```

---

### Get Seeds

```http
GET /api/seeds
```

---

### Get Climate

```http
GET /api/climate
```

---

### Get Reviews

```http
GET /api/reviews
```

---

### Submit Review

```http
POST /api/reviews
```

---

### Recommendation Engine

```http
POST /api/predict
```

---

# 15. Technology Stack

## Frontend

* React
* Tailwind CSS
* JavaScript/TypeScript
* Chart.js
* Leaflet (optional)

## Backend

* Python
* FastAPI
* REST APIs
* Uvicorn

## Database

Prototype options:

* PostgreSQL
* Firebase

## AI/ML

* Python
* Recommendation algorithms
* Collaborative filtering
* Similarity scoring
* Knowledge graph

## Deployment

* Vercel
* Render

---

# 16. Complete Data Flow

```text
                  FARMER
                     │
                     ▼
             Select Location
             Select Crop
             Select Conditions
                     │
                     ▼
                FRONTEND
                     │
                     ▼
                 FASTAPI
                     │
          ┌──────────┼──────────┐
          ▼          ▼          ▼
       Climate      Seeds     Reviews
        Data         Data       Data
          │          │          │
          └──────────┼──────────┘
                     ▼
              KNOWLEDGE GRAPH
                     │
                     ▼
            RECOMMENDATION AI
                     │
                     ▼
             RANK SEED VARIETIES
                     │
                     ▼
              TOP RECOMMENDATIONS
                     │
                     ▼
                  FARMER
                     │
                     ▼
               CROP OUTCOME
                     │
                     ▼
                NEW REVIEW
                     │
                     ▼
                DATABASE
```

---

# 17. Development Workflow

The five members can work in parallel.

### Phase 1

**Anushree**

* Frontend structure
* UI/UX
* Dashboard
* Components

**Anushka**

* FastAPI setup
* API structure
* Backend foundation

**Nakul**

* Database schema
* Seed dataset
* Climate dataset
* Review dataset
* Knowledge graph

These three can start simultaneously.

### Phase 2

**Sam**

Uses Nakul's structured data to build:

* Recommendation algorithm
* Similarity scoring
* Collaborative filtering
* Seed ranking

**Anushka**

Connects:

```text
Backend ↔ Database
Backend ↔ AI
```

### Phase 3

**Anushree**

Connects:

```text
Frontend ↔ Backend APIs
```

**Sparshh**

Connects and tests:

```text
Frontend
   ↓
Backend
   ↓
Database
   ↓
Knowledge Graph
   ↓
AI Engine
```

Then handles:

* Integration
* Testing
* Deployment
* Documentation
* Final demo
* Pitch preparation

---

# 18. Team Responsibilities

| Member       | Role                                | Main Responsibility                                     |
| ------------ | ----------------------------------- | ------------------------------------------------------- |
| **Anushree** | Frontend Developer                  | UI/UX, dashboard, components, API integration           |
| **Anushka**  | Backend Developer                   | FastAPI, REST APIs, data flow                           |
| **Nakul**    | Database & Knowledge Graph Engineer | Database, datasets, relationships, knowledge graph      |
| **Sam**      | AI & Recommendation Lead            | Recommendation engine, collaborative filtering, ranking |
| **Sparshh**  | DevOps, Integration & Product Lead  | Integration, testing, deployment, documentation, pitch  |

---

# 19. Task Dependency

```text
Nakul
Database + Knowledge Graph
        │
        ▼
Sam
AI Recommendation Engine
        │
        ▼
Anushka
Backend + AI/API Integration
        │
        ▼
Anushree
Frontend + API Integration
        │
        ▼
Sparshh
Final Integration + Testing + Deployment
```

However, this is **not a completely sequential process**.

Frontend, backend and database development should begin together using mock data and predefined API contracts.

---

# 20. Expected Outcomes

## Short-Term

The hackathon prototype will deliver:

* Working SeedBank AI website
* Recommendation dashboard
* Seed library
* Climate dashboard
* Farmer review system
* Knowledge graph prototype
* AI recommendation engine
* Backend APIs
* Database
* Live deployed prototype

## Long-Term

SeedBank AI can evolve into a larger agricultural decision-support platform with:

* Real-time climate APIs
* Government agricultural datasets
* Real seed/genetics databases
* Satellite data
* Soil data
* Weather forecasting
* More crops
* More regions
* Mobile application
* Local-language support
* Voice-based farmer interaction

---

# 21. Scalability

The architecture is designed so that the prototype can grow from:

```text
Prototype
   ↓
One Region
   ↓
Multiple Districts
   ↓
Multiple States
   ↓
National Platform
   ↓
Potential Global Climate-Resilient
Agriculture Platform
```

The same architecture can support more:

* Farmers
* Crops
* Seeds
* Locations
* Climate datasets
* Reviews
* Agricultural organisations

---

# 22. Business Model

### Freemium

Farmers can access basic recommendations for free.

Advanced features can potentially be offered through premium plans.

### Institutional Licensing

SeedBank AI can provide technology or analytics to:

* Seed companies
* Government departments
* NGOs
* Agricultural organisations
* Research institutions

### Potential Partnership

Seed companies and agricultural organisations can contribute verified data while the platform provides climate-aware recommendation infrastructure.

---

# 23. Unique Innovation

The central innovation is:

> **Seed selection based not only on where a farmer is today, but also on where the local climate is heading.**

SeedBank AI combines four important layers:

```text
             SeedBank AI
                  │
     ┌────────────┼────────────┐
     │            │            │
 Climate       Knowledge    Farmer
 Intelligence    Graph      Outcomes
     │            │            │
     └────────────┼────────────┘
                  │
           Recommendation AI
                  │
                  ▼
        Climate-Resilient Seeds
```

---

# 24. Why SeedBank AI is Different

Traditional approach:

```text
Farmer
  ↓
Generic Agricultural Advice
  ↓
Seed Selection
```

SeedBank AI:

```text
Farmer
  ↓
Location + Crop + Conditions
  ↓
Climate Trajectory
  +
Seed Characteristics
  +
Knowledge Graph
  +
Farmer Outcomes
  ↓
AI Recommendation
  ↓
Explainable Seed Selection
```

---

# 25. Future Scope

Possible future features include:

### Real Climate APIs

Automatically fetch local climate and weather information.

### Satellite Integration

Use satellite/environmental data for:

* Crop conditions
* Soil indicators
* Vegetation health
* Drought monitoring

### Multilingual Interface

Support regional languages such as:

* Marathi
* Hindi
* Tamil
* Telugu
* Kannada
* Bengali

### Voice Assistant

Farmers could ask:

> "Which soybean seed should I plant this season?"

and receive a voice-based recommendation.

### Mobile Application

Android/iOS application for easier field access.

### Verified Farmer Network

Verified crop outcomes could improve recommendation reliability.

---

# 26. Limitations of the Prototype

The hackathon prototype may use:

* Mock seed data
* Simulated climate projections
* Sample farmer reviews
* Simplified recommendation scoring

Therefore, prototype recommendation scores should **not be treated as certified agricultural advice**.

Before real-world deployment, the system would require:

* Verified agricultural datasets
* Expert validation
* Reliable climate projections
* Field testing
* Regional agricultural partnerships
* Model validation
* Appropriate safety and liability considerations

---

# 27. Project Vision

SeedBank AI aims to move agricultural seed selection from:

> **“What worked here before?”**

to:

> **“What is more likely to work here as the climate changes?”**

The long-term vision is to build an intelligent agricultural recommendation layer that helps farmers make **data-driven, climate-resilient seed decisions**.

---

# 28. Conclusion

**SeedBank AI combines AI, climate intelligence, knowledge graphs and real farmer outcomes to create personalised seed recommendations.**

Instead of relying only on historical agricultural advice, the platform helps farmers consider the **changing climate of their region**, making seed selection more adaptive, explainable and data-driven.

> **SeedBank AI: Choose the seed for the climate ahead.**

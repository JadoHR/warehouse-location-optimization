# 🚚 Warehouse Location Optimization — Indonesia
**Supply Chain & Logistics Optimization**

This project solves the warehouse location problem across Indonesia using data-driven optimization techniques. The goal is to identify the optimal set of warehouse locations that minimizes total logistics cost while meeting national demand.

## Methods Used

| Method | Purpose | Library |
|--------|---------|---------|
| **Haversine Distance** | Accurate city-to-city distance on Earth's surface (km) | NumPy |
| **K-Means Clustering** | Group cities by geographic and demand profile | scikit-learn |
| **Greedy Selection** | Iteratively pick warehouses minimizing total cost | Pandas/NumPy |
| **Map Visualization** | Plot demand distribution and warehouse coverage | Matplotlib |

## Project Structure

```
supply-chain-logistics/
├── data/
│   ├── indonesia_cities_demand.csv    # 30 Indonesian cities with demand data
│   └── warehouse_candidates.csv       # 10 potential warehouse locations
└── notebooks/
    └── warehouse_optimization.ipynb   # Full analysis + maps
```

## Datasets

### `indonesia_cities_demand.csv` — 30 Cities
| Column | Description |
|--------|-------------|
| `city`, `province`, `island` | Location info |
| `latitude`, `longitude` | Geographic coordinates |
| `demand_units` | Annual demand (units) |
| `population_2023` | City population |
| `gdp_per_capita_million_idr` | GDP per capita (Million IDR) |
| `distance_to_nearest_port_km` | Proximity to seaport |
| `logistics_cost_index` | Relative logistics cost (1.0 = baseline) |

### `warehouse_candidates.csv` — 10 Candidate Locations
| Column | Description |
|--------|-------------|
| `fixed_cost_million_idr` | Annual fixed operating cost |
| `capacity_units` | Max units handled per year |
| `near_toll`, `near_port`, `near_airport` | Accessibility flags |

## Getting Started

```bash
jupyter notebook notebooks/warehouse_optimization.ipynb
```

## Output Charts

- 🗺️ Indonesia demand map (circle size = demand volume)
- 📊 Elbow method for optimal cluster count
- 🎯 K-Means city clustering map
- 📉 Cost reduction curve per warehouse added
- 🏭 Final optimal warehouse map with service areas
- 💰 Transport cost vs fixed cost breakdown

## Requirements

```
pandas
numpy
matplotlib
scikit-learn
```

## Key Insights

- **4 optimal warehouses** selected: North Jakarta, Surabaya, Medan, Makassar
- Java accounts for over **60% of total national demand**
- Adding a 3rd and 4th warehouse produces the highest marginal cost reduction
- Highest logistics cost cities: **Papua, Maluku, East Nusa Tenggara** (remote islands)

## Haversine Formula

```
d = 2R × arcsin(√[sin²(Δφ/2) + cos φ₁ · cos φ₂ · sin²(Δλ/2)])
```

Where R = 6,371 km (Earth's radius), φ = latitude, λ = longitude.

---
*Dataset based on Indonesian demographic and geographic data, 2023*

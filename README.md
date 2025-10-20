# Nigerian Migration Pattern

This project analyzes **state-to-state migration flows** in Nigeria using survey data (`.sav` files) for men and women.  
It includes data cleaning, transformation, summary statistics, heatmaps, Sankey diagrams, and geospatial flow visualizations.

---

## 📂 Dataset
The repo expects the following files inside `men_and_womens_mobility_data/`:

- `mn.sav` → Men’s migration data  
- `wm.sav` → Women’s migration data  

Each file contains survey responses where:
- **MWB17 / WB17** → Previous state before moving  
- **HH7** → Current state of residence  

---

## ⚙️ Setup Instructions (with uv)

1. **Clone the repository**
   ```bash
   git clone <your-repo-url>
   cd <your-repo-folder>
   ```

2. **Install dependencies with uv**
   ```bash
   uv sync
   ```

   This will automatically create a `.venv` inside your project and install all required packages.

3. **Activate the virtual environment**
   ```bash
   source .venv/bin/activate     # Linux / macOS
   .venv\Scripts\activate        # Windows
   ```

4. **Run Jupyter Notebook**
   ```bash
   uv run jupyter notebook
   ```
   Open the analysis notebook (e.g., `migration_analysis.ipynb`).

---

## ▶️ Notebook Workflow

1. **Import Libraries** → `pandas`, `pyreadstat`, `seaborn`, `matplotlib`, `plotly`  
2. **Load Data** → Import `.sav` survey files  
3. **Extract Relevant Columns** → Previous & Current states for men and women  
4. **Filter & Clean Data** → Keep valid state codes (1–37)  
5. **Summary Statistics** → Unique values, frequencies  
6. **Migration Matrices** → Crosstab tables  
7. **Combine Men & Women** → Unified dataset with `PrevPlace` and `CurrentPlace`  
8. **State Mapping** → Map SPSS codes (1–37) to Nigerian state names  
9. **Visualizations**:  
   - Heatmap with Seaborn  
   - Checkerboard matrix with Matplotlib  
   - Sankey Diagram with Plotly  
   - Geospatial Flow Map (highlighting Ondo, Bauchi, Edo)  

---

## 📊 Outputs

- **Heatmaps** → Migration intensity between Nigerian states  
- **Sankey Diagram** → State-to-state migration flows  
- **Geo Map with Flow Lines** → Visualizes migration paths across Nigeria  
- **Highlighted States** → Ondo, Bauchi, Edo with distinct markers and percentages  

Example stats:
```
Total Migrants: 30,416
    State   Count  Percentage
Ondo      977   3.21%
Bauchi   1000   3.29%
Edo       896   2.95%
```

---

## 📦 Dependencies

All dependencies are declared in `pyproject.toml` and resolved via **uv**.  
Core libraries include:

- pandas  
- pyreadstat  
- seaborn  
- matplotlib  
- plotly  

---

## ✨ Notes
- Place `.sav` files under `men_and_womens_mobility_data/`.  
- Migration codes **96 / 99** are treated as invalid and dropped.  
- FCT is mapped as `"FCT"` in the dataset and `"Federal Capital Territory"` in maps.  

---

## 📍 Next Steps
- Extend mapping to match external GeoJSON for choropleth maps.  
- Add interactive dashboards with Plotly Dash or Streamlit.  
- Compare migration patterns across gender or age groups.  

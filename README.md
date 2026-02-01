# Movie Ratings Analysis
## Task 2 - Data Science Internship at Hex Softwares

A comprehensive data analysis project demonstrating exploratory data analysis, statistical reasoning, and data visualization skills through the analysis of movie ratings data.

---

## 📋 Project Overview

This project analyzes movie ratings data to uncover meaningful trends and patterns that help stakeholders understand:
- Movie rating distributions and trends
- Genre-based performance insights
- Relationships between ratings, revenue, and other features
- Statistical patterns and anomalies

**Key Principles:**
- **Clarity** – Visuals are easy to interpret
- **Accuracy** – No misleading representations
- **Efficiency** – Maximum insight with minimum cognitive load

---

## 🎯 Objectives

1. Perform comprehensive data cleaning and preprocessing
2. Conduct statistical analysis on movie ratings
3. Extract genre-based insights
4. Analyze relationships between ratings, revenue, and features
5. Create professional visualizations
6. Build an interactive Power BI dashboard

---

## 🛠️ Technologies Used

- **Python 3.11+**
- **Jupyter Notebook** - Interactive analysis environment
- **Pandas** - Data manipulation and analysis
- **NumPy** - Numerical computing
- **Matplotlib** - Data visualization
- **Seaborn** - Statistical visualizations
- **Power BI** - Interactive dashboard

---

## 📁 Project Structure

```
Task_2_Movie_Ratings_Analysis/
│
├── data/
│   ├── raw/                          # Original datasets
│   └── cleaned/                      # Processed data
│       ├── movies_cleaned.csv        # Main cleaned dataset
│       ├── genre_analysis.csv        # Genre frequency data
│       ├── genre_performance.csv     # Genre performance metrics
│       └── summary_statistics.csv    # Statistical summaries
│
├── notebooks/
│   └── Movie_Ratings_Analysis.ipynb  # Main analysis notebook
│
├── visualizations/                   # Generated charts and plots
│   ├── missing_values.png
│   ├── genre_distribution.png
│   ├── genre_performance.png
│   ├── correlation_heatmap.png
│   ├── rating_vs_revenue.png
│   ├── rating_distribution.png
│   ├── runtime_distribution.png
│   ├── boxplots_outliers.png
│   └── comprehensive_dashboard.png
│
├── powerbi/
│   ├── Movie_Dashboard.pbix          # Power BI dashboard file
│   └── PowerBI_Dashboard_Guide.md    # Dashboard creation guide
│
├── requirements.txt                  # Python dependencies
└── README.md                         # This file
```

---

## 🚀 Getting Started

### Prerequisites

- Python 3.11 or higher
- Jupyter Notebook
- Power BI Desktop (for dashboard)

### Installation

1. **Clone or navigate to the project directory:**
   ```bash
   cd d:\HexSoftwares\Task_2_Movie_Ratings_Analysis
   ```

2. **Create a virtual environment (recommended):**
   ```bash
   python -m venv venv
   venv\Scripts\activate  # On Windows
   ```

3. **Install dependencies:**
   ```bash
   pip install -r requirements.txt
   ```

4. **Launch Jupyter Notebook:**
   ```bash
   jupyter notebook
   ```

5. **Open the analysis notebook:**
   - Navigate to `notebooks/Movie_Ratings_Analysis.ipynb`
   - Run all cells sequentially

---

## 📊 Analysis Workflow

### 1. Data Loading
- Import IMDB movie dataset
- Display first 10 rows for structure understanding
- Initial data exploration

### 2. Data Exploration
- Inspect data types with `info()`
- Identify unique values with `nunique()`
- Determine categorical vs numerical columns

### 3. Data Cleaning
- **Missing Values:**
  - Detect with `isnull().sum()`
  - Calculate percentage of missing data
  - Drop rows if missing ≤7%, otherwise impute
  
- **Duplicates:**
  - Detect and remove duplicate entries
  - Ensure data integrity

### 4. Statistical Analysis
- Generate comprehensive statistics with `describe(include='all')`
- Calculate mean, median, mode of ratings
- Identify highest revenue movies with `nlargest()`
- Find top-rated movies

### 5. Genre Analysis
- Extract and normalize genre data
- Handle multi-genre entries
- Calculate genre frequency with `value_counts()`
- Analyze genre-wise performance

### 6. Relationship Analysis
- Create correlation matrix
- Analyze rating vs revenue relationship
- Perform genre-wise performance breakdown
- Identify statistical patterns

### 7. Visualizations
- **Distribution Plots:** Ratings, runtime, revenue
- **Box Plots:** Outlier detection
- **Heatmaps:** Correlation analysis
- **Scatter Plots:** Relationship visualization
- **Comprehensive Dashboard:** Multi-panel summary

### 8. Power BI Dashboard
- Import cleaned data
- Create interactive visuals
- Add filters and slicers
- Design executive-friendly layout

---

## 📈 Key Visualizations

### Generated Visualizations

1. **Missing Values Analysis** - Bar chart showing missing data percentages
2. **Genre Distribution** - Top 15 most frequent genres
3. **Genre Performance** - Average ratings and movie counts by genre
4. **Correlation Heatmap** - Relationships between numerical features
5. **Rating vs Revenue** - Scatter plot with genre coloring and trend line
6. **Rating Distribution** - Histogram with mean/median indicators
7. **Runtime Distribution** - Distribution of movie lengths
8. **Outlier Detection** - Box plots for rating, revenue, and runtime
9. **Comprehensive Dashboard** - Multi-panel overview of all insights

All visualizations are saved in the `visualizations/` directory at 300 DPI for publication quality.

---

## 📊 Power BI Dashboard

The Power BI dashboard provides an interactive, executive-level view of the analysis with:

### Features
- **KPI Cards:** Total movies, average rating, total revenue
- **Genre Analysis:** Distribution, performance, trends over time
- **Rating & Revenue:** Scatter plots, distributions, correlations
- **Interactive Filters:** Genre, year, rating range
- **Cross-filtering:** Click any visual to filter all others

### Pages
1. **Executive Overview** - High-level metrics and top movies
2. **Genre Deep Dive** - Detailed genre performance analysis
3. **Rating & Revenue Analysis** - Relationship exploration

See `powerbi/PowerBI_Dashboard_Guide.md` for detailed creation instructions.

---

## 📝 Key Findings

The analysis reveals:

1. **Rating Patterns:**
   - Distribution of movie ratings
   - Central tendency and variability
   - Outliers and exceptional movies

2. **Genre Insights:**
   - Most popular genres
   - Highest-rated genres
   - Genre performance trends

3. **Revenue Relationships:**
   - Correlation between ratings and revenue
   - Top-grossing movies
   - Revenue distribution patterns

4. **Statistical Insights:**
   - Data quality metrics
   - Feature correlations
   - Outlier identification

*(Specific findings will be generated when you run the notebook)*

---

## 🔧 Customization

### Using Your Own Dataset

1. Replace the data URL in the notebook:
   ```python
   data_url = "your_dataset_url_or_path.csv"
   ```

2. Ensure your dataset has similar columns:
   - Movie name/title
   - Rating/score
   - Revenue/gross
   - Genre
   - Year
   - Runtime (optional)

3. Run all cells - the code adapts to column names automatically

### Modifying Visualizations

- Adjust color schemes in the visualization settings
- Change figure sizes with `plt.rcParams['figure.figsize']`
- Modify plot styles with `plt.style.use()`

---

## 📚 Dependencies

```
pandas>=2.0.0
numpy>=1.24.0
matplotlib>=3.7.0
seaborn>=0.12.0
jupyter>=1.0.0
openpyxl>=3.1.0
kaggle>=1.5.16
```

Install all with: `pip install -r requirements.txt`

---

## 🎓 Learning Outcomes

This project demonstrates:

✅ **Data Cleaning:** Handling missing values, duplicates, and data quality issues  
✅ **Statistical Analysis:** Descriptive statistics, correlation, distribution analysis  
✅ **Data Visualization:** Creating clear, accurate, and efficient visualizations  
✅ **Genre Analysis:** String manipulation, categorical data analysis  
✅ **Relationship Analysis:** Correlation, scatter plots, trend analysis  
✅ **Dashboard Design:** Executive-level reporting with Power BI  
✅ **Code Quality:** Well-commented, organized, and reproducible analysis  

---

## 🤝 Contributing

This is an internship project, but suggestions for improvement are welcome:

1. Fork the repository
2. Create a feature branch
3. Make your changes
4. Submit a pull request

---

## 📄 License

This project is created for educational purposes as part of the Data Science Internship at Hex Softwares.

---

## 👤 Author

**Data Science Intern**  
Hex Softwares  
Task 2 - Movie Ratings Analysis  
February 2026

---

## 🙏 Acknowledgments

- **IMDB** for providing the movie dataset
- **Hex Softwares** for the internship opportunity
- **Python Community** for excellent data science libraries

---

## 📞 Support

For questions or issues:
1. Check the Jupyter Notebook comments
2. Review the Power BI Dashboard Guide
3. Consult the implementation plan
4. Reach out to your internship supervisor

---

**Happy Analyzing! 📊🎬**

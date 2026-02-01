# Quick Start Guide
## Movie Ratings Analysis Project

This guide helps you get started quickly with the analysis.

---

## ⚡ Quick Start (5 Minutes)

### Option 1: Run the Analysis

```bash
# 1. Navigate to project directory
cd d:\HexSoftwares\Task_2_Movie_Ratings_Analysis

# 2. Install dependencies
pip install -r requirements.txt

# 3. Launch Jupyter Notebook
jupyter notebook

# 4. Open and run the notebook
# Navigate to: notebooks/Movie_Ratings_Analysis.ipynb
# Click: Cell → Run All
```

### Option 2: Using Virtual Environment (Recommended)

```bash
# 1. Navigate to project directory
cd d:\HexSoftwares\Task_2_Movie_Ratings_Analysis

# 2. Create virtual environment
python -m venv venv

# 3. Activate virtual environment
venv\Scripts\activate  # Windows
# source venv/bin/activate  # Mac/Linux

# 4. Install dependencies
pip install -r requirements.txt

# 5. Launch Jupyter Notebook
jupyter notebook
```

---

## 📊 What Happens When You Run the Notebook?

The notebook will automatically:

1. ✅ Load movie ratings dataset from online source
2. ✅ Clean and preprocess the data
3. ✅ Perform statistical analysis
4. ✅ Analyze genres and their performance
5. ✅ Create 9+ professional visualizations
6. ✅ Generate a comprehensive dashboard
7. ✅ Export cleaned data for Power BI

**Estimated Runtime:** 2-3 minutes

---

## 📁 Output Files

After running the notebook, you'll find:

### Cleaned Data (in `data/cleaned/`)
- `movies_cleaned.csv` - Main dataset for Power BI
- `genre_analysis.csv` - Genre frequency data
- `genre_performance.csv` - Genre performance metrics
- `summary_statistics.csv` - Statistical summaries

### Visualizations (in `visualizations/`)
- `missing_values.png`
- `genre_distribution.png`
- `genre_performance.png`
- `correlation_heatmap.png`
- `rating_vs_revenue.png`
- `rating_distribution.png`
- `runtime_distribution.png`
- `boxplots_outliers.png`
- `comprehensive_dashboard.png`

---

## 🎨 Power BI Dashboard (Next Step)

After running the notebook:

1. **Open Power BI Desktop**
2. **Import Data:**
   - File → Get Data → Text/CSV
   - Select: `data/cleaned/movies_cleaned.csv`
3. **Follow the Guide:**
   - Open: `powerbi/PowerBI_Dashboard_Guide.md`
   - Follow step-by-step instructions

**Estimated Time:** 30-45 minutes

---

## 🔧 Troubleshooting

### Issue: Jupyter Notebook not found
```bash
pip install jupyter
```

### Issue: Module not found errors
```bash
pip install -r requirements.txt --upgrade
```

### Issue: Dataset download fails
The notebook uses an online dataset. If it fails:
1. Check your internet connection
2. The notebook will show the error
3. You can manually download a dataset and update the URL in the notebook

### Issue: Visualizations not saving
- Ensure the `visualizations/` folder exists
- Check write permissions
- The notebook creates the folder automatically

---

## 📚 Project Structure

```
Task_2_Movie_Ratings_Analysis/
├── data/
│   ├── raw/              # Original data
│   └── cleaned/          # Processed data (generated)
├── notebooks/
│   └── Movie_Ratings_Analysis.ipynb  # Main notebook
├── visualizations/       # Charts (generated)
├── powerbi/
│   ├── PowerBI_Dashboard_Guide.md
│   └── Movie_Dashboard.pbix  # Create this
├── requirements.txt
└── README.md
```

---

## ✅ Checklist

Before starting:
- [ ] Python 3.11+ installed
- [ ] Internet connection (for dataset download)
- [ ] 500MB free disk space
- [ ] Power BI Desktop (for dashboard)

After running notebook:
- [ ] All cells executed without errors
- [ ] 9 visualization files created
- [ ] 4 CSV files exported to `data/cleaned/`
- [ ] Ready to create Power BI dashboard

---

## 🎯 Next Steps

1. ✅ Run the Jupyter Notebook
2. ✅ Review generated visualizations
3. ✅ Check cleaned data exports
4. ⏭️ Create Power BI dashboard
5. ⏭️ Present findings

---

## 💡 Tips

- **First Time?** Run all cells once to see the full analysis
- **Customizing?** Modify color schemes, chart types as needed
- **Different Data?** Update the `data_url` variable in Section 2
- **Presentation?** Use the comprehensive dashboard PNG for slides

---

## 📞 Need Help?

1. Check the main `README.md`
2. Review notebook comments
3. Consult `PowerBI_Dashboard_Guide.md`
4. Contact your supervisor

---

**Ready to analyze! 🚀**

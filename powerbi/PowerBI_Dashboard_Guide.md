# Power BI Dashboard Guide
## Movie Ratings Analysis - Task 2

This guide provides step-by-step instructions for creating the interactive Power BI dashboard.

---

## Prerequisites

- Power BI Desktop installed (Download from: https://powerbi.microsoft.com/desktop/)
- Completed Jupyter Notebook analysis
- Cleaned data files in `data/cleaned/` directory

---

## Step 1: Import Data

1. **Open Power BI Desktop**

2. **Get Data**
   - Click "Get Data" → "Text/CSV"
   - Navigate to: `data/cleaned/movies_cleaned.csv`
   - Click "Load"

3. **Verify Data Import**
   - Check row count matches the cleaned dataset
   - Verify all columns are present
   - Ensure data types are correct (Rating: Decimal, Revenue: Whole Number, etc.)

---

## Step 2: Data Modeling (Optional)

### Create Calculated Columns

**Revenue in Millions:**
```DAX
Revenue_Millions = [gross] / 1000000
```

**Rating Category:**
```DAX
Rating_Category = 
IF([score] >= 8, "Excellent",
IF([score] >= 7, "Good",
IF([score] >= 6, "Average", "Below Average")))
```

**Decade:**
```DAX
Decade = FLOOR([year], 10)
```

### Create Measures

**Average Rating:**
```DAX
Avg_Rating = AVERAGE('movies_cleaned'[score])
```

**Total Revenue:**
```DAX
Total_Revenue = SUM('movies_cleaned'[gross])
```

**Movie Count:**
```DAX
Movie_Count = COUNTROWS('movies_cleaned')
```

---

## Step 3: Page 1 - Executive Overview

### Layout Structure
```
┌─────────────────────────────────────────────────────┐
│  MOVIE RATINGS ANALYSIS - EXECUTIVE DASHBOARD       │
├──────────┬──────────┬──────────┬───────────────────┤
│ Total    │ Avg      │ Total    │                   │
│ Movies   │ Rating   │ Revenue  │   Filters Panel   │
│ (KPI)    │ (KPI)    │ (KPI)    │                   │
├──────────┴──────────┴──────────┴───────────────────┤
│                                                     │
│  Genre Distribution (Pie Chart)                     │
│                                                     │
├─────────────────────────────────────────────────────┤
│                                                     │
│  Top 10 Rated Movies (Table)                        │
│                                                     │
└─────────────────────────────────────────────────────┘
```

### Visuals to Create

**1. KPI Cards (Top Row)**
- **Total Movies**
  - Visual: Card
  - Field: Movie_Count measure
  - Format: Whole number with comma separator

- **Average Rating**
  - Visual: Card
  - Field: Avg_Rating measure
  - Format: 1 decimal place

- **Total Revenue**
  - Visual: Card
  - Field: Total_Revenue measure
  - Format: Currency, millions

**2. Genre Distribution**
- Visual: Pie Chart or Donut Chart
- Legend: primary_genre
- Values: Count of movies
- Colors: Use "Diverging" color scheme

**3. Top 10 Rated Movies**
- Visual: Table
- Columns: name, year, score, gross, primary_genre
- Sort: By score (descending)
- Top N Filter: 10

**4. Filters Panel (Right Side)**
- Genre Slicer (Dropdown or List)
- Year Slicer (Range slider)
- Rating Slicer (Range slider)

---

## Step 4: Page 2 - Genre Deep Dive

### Visuals to Create

**1. Genre-wise Average Rating**
- Visual: Horizontal Bar Chart
- Axis: primary_genre
- Values: Avg_Rating
- Sort: By average rating (descending)
- Filter: Show only genres with ≥5 movies

**2. Genre-wise Total Revenue**
- Visual: Column Chart
- Axis: primary_genre
- Values: Total_Revenue
- Sort: By revenue (descending)
- Top N: 10

**3. Genre Popularity Over Time**
- Visual: Stacked Area Chart
- Axis: year
- Legend: primary_genre (top 5 genres)
- Values: Count of movies

**4. Genre Performance Matrix**
- Visual: Scatter Chart
- X-Axis: Avg_Rating
- Y-Axis: Total_Revenue
- Legend: primary_genre
- Size: Movie_Count

---

## Step 5: Page 3 - Rating & Revenue Analysis

### Visuals to Create

**1. Rating vs Revenue Scatter**
- Visual: Scatter Chart
- X-Axis: score
- Y-Axis: gross
- Legend: primary_genre
- Size: runtime (if available)
- Play Axis: year (for animation)

**2. Rating Distribution**
- Visual: Histogram
  - Create bins: 0-2, 2-4, 4-6, 6-8, 8-10
  - Or use Column Chart with score on X-axis
- Values: Count of movies

**3. Revenue Distribution**
- Visual: Box and Whisker Plot (if available)
- Or use Column Chart with revenue bins
- Category: Revenue_Millions (binned)

**4. Correlation Matrix**
- Visual: Matrix or Heatmap (custom visual)
- Rows: Metrics (Rating, Revenue, Runtime)
- Columns: Metrics
- Values: Correlation values

---

## Step 6: Design & Formatting

### Color Scheme (Executive-Friendly)
- **Primary:** #1F4788 (Navy Blue)
- **Secondary:** #4A90E2 (Sky Blue)
- **Accent:** #F39C12 (Orange)
- **Success:** #27AE60 (Green)
- **Background:** #F8F9FA (Light Gray)

### Typography
- **Title:** Segoe UI Bold, 18pt
- **Headers:** Segoe UI Semibold, 14pt
- **Body:** Segoe UI Regular, 11pt

### General Formatting Tips
1. **Remove Gridlines** - Cleaner look
2. **Add Data Labels** - For key metrics
3. **Use Tooltips** - Add custom tooltips with additional context
4. **Consistent Spacing** - Align all visuals to grid
5. **White Space** - Don't overcrowd the dashboard

---

## Step 7: Add Interactivity

### Cross-Filtering
- Enable cross-filtering between all visuals
- Click on a genre → all visuals filter to that genre

### Drill-Through
1. Create a "Movie Details" page
2. Add drill-through field: movie name
3. Show detailed information when user right-clicks a movie

### Bookmarks
- Create bookmarks for different views:
  - "All Movies"
  - "High Rated Only" (score ≥ 7)
  - "Top Grossing" (top 100 by revenue)

---

## Step 8: Publish & Share

### Save the Dashboard
- File → Save As
- Location: `powerbi/Movie_Dashboard.pbix`

### Publish to Power BI Service (Optional)
1. Sign in to Power BI account
2. Click "Publish"
3. Select workspace
4. Share link with stakeholders

---

## Troubleshooting

### Data Not Loading
- Verify CSV file path is correct
- Check for special characters in file path
- Ensure CSV is properly formatted

### Visuals Not Updating
- Refresh data: Home → Refresh
- Check filters are not too restrictive
- Verify relationships between tables (if using multiple tables)

### Performance Issues
- Reduce number of visuals per page (max 8-10)
- Use aggregated data instead of row-level
- Optimize DAX measures

---

## Best Practices

✅ **Keep it Simple** - Don't overcomplicate with too many visuals  
✅ **Tell a Story** - Arrange visuals in logical flow  
✅ **Use Consistent Colors** - Maintain color scheme across all pages  
✅ **Add Context** - Include titles, labels, and descriptions  
✅ **Test Interactivity** - Ensure all filters and slicers work correctly  
✅ **Mobile View** - Design a mobile-optimized layout  

---

## Example DAX Formulas

### Top N Filter
```DAX
Top_10_Movies = 
TOPN(10, 
     ALL('movies_cleaned'), 
     'movies_cleaned'[score], 
     DESC)
```

### Year-over-Year Growth
```DAX
Revenue_YoY = 
VAR CurrentYear = MAX('movies_cleaned'[year])
VAR PreviousYear = CurrentYear - 1
VAR CurrentRevenue = CALCULATE(SUM('movies_cleaned'[gross]), 'movies_cleaned'[year] = CurrentYear)
VAR PreviousRevenue = CALCULATE(SUM('movies_cleaned'[gross]), 'movies_cleaned'[year] = PreviousYear)
RETURN
DIVIDE(CurrentRevenue - PreviousRevenue, PreviousRevenue, 0)
```

### Genre Rank
```DAX
Genre_Rank = 
RANKX(
    ALL('movies_cleaned'[primary_genre]),
    CALCULATE(AVERAGE('movies_cleaned'[score])),
    ,
    DESC
)
```

---

## Resources

- **Power BI Documentation:** https://docs.microsoft.com/power-bi/
- **DAX Reference:** https://dax.guide/
- **Community Forum:** https://community.powerbi.com/
- **Video Tutorials:** https://www.youtube.com/powerbi

---

*Created for Task 2 - Data Science Internship at Hex Softwares*

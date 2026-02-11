# Student Performance Analysis: Grade Distribution and Class Trends

A comprehensive analysis of student academic performance using Python, examining grade distributions, class-level performance patterns, and gender-based score differences across multiple numerically labelled classrooms.

## Visualizations

### Grade Distribution
![Grade Distribution](Screenshot_2026-02-05_121922.png)

### Average Scores by Class and Gender
![Average Scores Heatmap](Screenshot_2026-02-05_122213.png)

### Score Distribution Across Classes
![Score Distribution by Class](Screenshot_2026-02-05_122036.png)

### Individual Student Performance
![Student Scores Colored by Grade](Screenshot_2026-02-05_122743.png)

## Key Findings

### Overall Grade Distribution
The analysis of grade distribution revealed a concentration of high-performing students:

- **Grade A dominates** with 40.0% of all students, indicating strong overall academic performance
- **Grade B** represents 25.7% of students, showing a solid middle-tier performance
- **Grades D and C** account for 20.0% and 14.3% respectively, suggesting some students need additional support

**Interpretation**: The heavy skew toward A grades (40%) may indicate either genuinely high-performing students or potential grade inflation that administrators should examine.

### Class-Level Performance Disparities
The heatmap analysis uncovered significant performance variations across different classes:

- **Highest performing classes**: Class Six (female: 89.2, male: 54.0) and Class Seven (female: 81.4, male: 73.8) show strong female performance
- **Critical concern - Class Nine**: Male students in Class Nine scored dramatically lower (18.0 average) compared to all other groups, suggesting a targeted intervention is needed
- **Gender patterns**: Female students in Class Four (63.8) and Class Nine (65.0) outperform their male counterparts, though male students excel in Classes Five, Eight, and Three

**Actionable Insight**: Class Nine males require immediate academic support or investigation into teaching methods, as their 18.0 average is an outlier that could indicate systemic issues.

### Score Variability Analysis
Box plot visualization revealed important patterns in score consistency:

- **Most consistent classes**: Classes Eight and Five show narrow score ranges with small interquartile ranges, suggesting uniform teaching effectiveness
- **Highest variability**: Class Nine exhibits the widest score distribution (ranging from ~18 to 65), indicating inconsistent student performance or possible external factors affecting learning
- **Outliers**: Class Six shows an outlier around 54, suggesting one student significantly underperformed relative to classmates

**Educational Application**: Schools can use this analysis to identify which classes need differentiated instruction strategies and which teaching approaches are producing consistent results.

## Methodology

**Tools and Libraries**:
- **Python 3.x**: Core programming language
- **Pandas**: Data manipulation and analysis
- **Matplotlib**: Data visualization (pie charts, scatter plots, box plots)
- **Seaborn**: Statistical visualizations (heatmap)
- **Google Colab**: Development and execution environment

**Analysis Approach**:
1. **Data Preparation**: Loaded student dataset containing student names, classes, scores, grades, and gender
2. **Exploratory Data Analysis**: 
   - Calculated grade distribution using `value_counts()`
   - Created pivot table to analyze average scores by class and gender
   - Generated box plots to examine score distributions and identify outliers
3. **Visualization Strategy**: Used multiple chart types to reveal different insights:
   - Pie chart for categorical distribution (grades)
   - Heatmap for multi-dimensional comparison (class vs. gender)
   - Box plot for statistical distribution analysis
   - Scatter plot for individual-level patterns

**Key Variables**:
- Student Name
- Class (Eight, Fifth, Five, Four, Nine, Seven, Six, Three)
- Score (numerical)
- Grade (A, B, C, D)
- Gender (male, female)

## Code Highlights

**Pie Chart with Custom Styling**:
```python
grade_counts = df['grade'].value_counts()
plt.figure(figsize=(8, 8))
colors = ['#ff9999', '#66b3ff', '#99ff99', '#ffcc99']
plt.pie(grade_counts, labels=grade_counts.index, autopct='%1.1f%%', 
        colors=colors, startangle=90, explode=[0.05, 0.05, 0.05, 0.05])
plt.title('Grade Distribution', fontsize=14, fontweight='bold')
```

**Heatmap Analysis**:
```python
pivot = df.pivot_table(values='score', index='class', columns='gender', aggfunc='mean')
sns.heatmap(pivot, annot=True, fmt='.1f', cmap='YlOrRd', 
            linewidths=1, cbar_kws={'label': 'Average Score'})
```

## Potential Extensions

- **Temporal Analysis**: Track performance changes over academic terms/semesters
- **Correlation Studies**: Examine relationships between attendance, homework completion, and final scores
- **Predictive Modeling**: Build machine learning models to predict at-risk students based on early performance indicators
- **Intervention Tracking**: Measure effectiveness of targeted support programs for underperforming classes

## Repository Contents

- Python notebook (`.ipynb`) with complete analysis code
- Visualization outputs (pie chart, heatmap, box plot, scatter plot)
- Student dataset (CSV format)
- README.md (this file)

## Educational Impact

This analysis demonstrates practical applications of data science in education:
- **Early Warning Systems**: Identifying struggling students before final grades are assigned
- **Resource Allocation**: Data-driven decisions about where to assign tutoring support
- **Teaching Effectiveness**: Comparing class-level performance to evaluate instructional methods
- **Equity Analysis**: Uncovering gender-based performance gaps that may require policy interventions

---

*This project showcases proficiency in Python data analysis, statistical visualization, and translating educational data into actionable recommendations for school administrators.*

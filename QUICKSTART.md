# Quick Start Guide - PCA Analysis

Get up and running with PCA analysis in 5 minutes!

## 🚀 Setup (2 minutes)

### 1. Clone the Repository
```bash
git clone https://github.com/yourusername/PCA-Lung-Cancer-Analysis.git
cd PCA-Lung-Cancer-Analysis
```

### 2. Create Virtual Environment
```bash
# Windows
python -m venv venv
venv\Scripts\activate

# Mac/Linux
python3 -m venv venv
source venv/bin/activate
```

### 3. Install Dependencies
```bash
pip install -r requirements.txt
```

**That's it!** ✅

---

## 🎯 Running the Analysis (1 minute)

### Option A: Simple Python Script
```bash
python main.py
```

**Output:**
```
- Console output with detailed analysis
- pca_analysis_results.png (visualization)
- pca_results.csv (transformed data)
```

### Option B: Jupyter Notebook (Interactive)
```bash
jupyter notebook PCA_Analysis.ipynb
```

Then click "Run All" to execute all cells.

---

## 📊 Understanding Your Output

### 1. Console Output
```
STEP 1: LOADING AND EXPLORING DATA
✓ Dataset loaded successfully!
  Dataset shape: (32, 15)

STEP 7: EXPLAINED VARIANCE ANALYSIS
PC1: 25.34%
PC2: 18.92%
```

**What to look for:**
- ✓ All steps completed without errors
- ✓ Numbers make sense for your data
- ✓ No warnings (unless expected)

### 2. pca_analysis_results.png

A 2×2 grid of plots:

| Plot | What it shows | What to look for |
|------|---|---|
| **Scree Plot** (top-left) | Variance by component | Elbow point, steepness |
| **PCA Projection** (top-right) | Data in 2D space | Class separation |
| **Loadings** (bottom-left) | Feature importance | Which features matter |
| **Variance** (bottom-right) | % per component | Information distribution |

### 3. pca_results.csv

```
PC1,PC2,Class
-2.34,1.12,1
0.56,0.89,2
1.23,-0.45,1
...
```

Use for further analysis or visualizations.

---

## 🔧 Customizing the Analysis

### Change Number of Components

**In `main.py`, find this line (around line 180):**
```python
n_components = 2  # Change this number
```

**Options:**
- `2` - For visualization (default)
- `3` - For 3D visualization
- `10` - To capture 95% variance
- `None` - For all components (then analyze)

### Change Variance Threshold

**Find the line:**
```python
VARIANCE_THRESHOLD = 0.95
```

**Options:**
- `0.90` - Keep 90% of information
- `0.95` - Keep 95% of information (default)
- `0.99` - Keep 99% of information

### Change Plot Style

**Find visualization settings:**
```python
FIGURE_SIZE = (14, 10)
DPI = 300
COLOR_PALETTE = 'viridis'
```

**Color palette options:**
- `'viridis'` - Blue to yellow (default)
- `'plasma'` - Purple to yellow
- `'cool'` - Cyan to pink
- `'hot'` - Black to red

---

## 🎓 Learning Path

### For Beginners
1. Read `README.md` - Understand what PCA is
2. Run `main.py` - See it in action
3. Look at outputs - Understand the results
4. Read `PCA_GUIDE.md` - Learn concepts

### For Students
1. Read `PCA_GUIDE.md` - Deep dive into theory
2. Run `PCA_Analysis.ipynb` - Interactive exploration
3. Modify code - Experiment with settings
4. Write report - Summarize findings

### For Practitioners
1. Adapt `main.py` to your data
2. Adjust number of components
3. Integrate into ML pipeline
4. Compare with other methods

---

## 🐛 Troubleshooting

### Error: "Module not found"
```
Solution: Make sure virtual environment is activated
Windows: venv\Scripts\activate
Mac/Linux: source venv/bin/activate
```

### Error: "URL Error" or "No internet"
```
Solution: Dataset couldn't download
Options:
1. Check internet connection
2. Download dataset manually and place in data/
3. Use local copy path in script
```

### Error: "Data shape mismatch"
```
Solution: Dataset format changed
Fix: Verify column_names match dataset structure
Check: First row of downloaded file
```

### Plot not showing
```
Solution: In Jupyter, run:
%matplotlib inline

Or use:
plt.show()
```

### Script runs but no output file
```
Solution: Check current working directory
Fix: Save to full path
results_df.to_csv('/full/path/pca_results.csv')
```

---

## 📚 File Reference

| File | Purpose | Read when |
|------|---------|-----------|
| `README.md` | Complete documentation | Starting out |
| `PCA_GUIDE.md` | Theory & concepts | Learning PCA |
| `QUICKSTART.md` | This file | Getting started |
| `main.py` | Main analysis script | Running analysis |
| `PCA_Analysis.ipynb` | Interactive notebook | Step-by-step learning |
| `data_utils.py` | Utility functions | Using helper functions |
| `config.py` | Settings & constants | Customizing analysis |
| `requirements.txt` | Dependencies | Installing packages |

---

## 💡 Quick Tips

### Tip 1: Always Standardize
```python
from sklearn.preprocessing import StandardScaler
scaler = StandardScaler()
X_scaled = scaler.fit_transform(X)  # DO THIS FIRST!
```

### Tip 2: Check Variance
```python
# See how much info each component has
print(pca.explained_variance_ratio_)
print(np.cumsum(pca.explained_variance_ratio_))
```

### Tip 3: Interpret Loadings
```python
# See which features are important
loadings = pca.components_.T * np.sqrt(pca.explained_variance_)
print(loadings[:, 0])  # PC1 loadings
```

### Tip 4: Save Everything
```python
# Save results for later
results.to_csv('pca_results.csv')
plt.savefig('pca_plot.png', dpi=300)
```

### Tip 5: Document Your Process
```
# Add comments to your code
# Log your decisions
# Save outputs with timestamps
```

---

## 🤔 Common Questions

### Q: How many components should I use?

**A:** Use the scree plot!
- Look for "elbow" point
- Or select for 95% variance
- Or use cross-validation

### Q: Why standardize?

**A:** Features on different scales bias PCA.
- Age: 0-100
- Income: 0-1,000,000
- StandardScaler puts both on -3 to 3 scale

### Q: Can I use PCA for classification?

**A:** Yes! Use pipeline:
```python
Pipeline([
    ('scaler', StandardScaler()),
    ('pca', PCA(n_components=10)),
    ('classifier', LogisticRegression())
])
```

### Q: Is PCA supervised or unsupervised?

**A:** Unsupervised. Doesn't use class labels.
Finds variance patterns in features only.

### Q: What if my data has categorical variables?

**A:** Encode first (one-hot or label encoding)
```python
df = pd.get_dummies(df)  # One-hot encoding
# Then apply PCA
```

---

## 📞 Getting Help

1. **Error in console?**
   - Read error message carefully
   - Search error message online
   - Check Troubleshooting section

2. **Confused about concept?**
   - Read `PCA_GUIDE.md`
   - Watch tutorial video
   - Read scikit-learn docs

3. **Results don't make sense?**
   - Double-check data quality
   - Verify feature scaling
   - Check number of components
   - Compare with domain knowledge

---

## 🎯 Next Steps

### After Analysis
1. ✅ Run the analysis
2. ✅ Examine outputs
3. ✅ Understand results
4. ✅ Draw conclusions
5. → Integrate into ML pipeline
6. → Compare with other methods
7. → Deploy to production

### Learn More
- [Scikit-learn PCA](https://scikit-learn.org/stable/modules/decomposition.html#pca)
- [StatQuest PCA Videos](https://www.youtube.com/watch?v=HMOI_lkzW08)
- [PCA Paper](https://arxiv.org/abs/1404.1100)

---

**Happy analyzing! 🚀**

*Last updated: September 2024*

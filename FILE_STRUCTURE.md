# Project File Structure

Complete guide to all files in the PCA Analysis project and their purposes.

## 📁 Directory Layout

```
PCA-Lung-Cancer-Analysis/
│
├── 📄 README.md                  # Main documentation
├── 📄 QUICKSTART.md              # Quick setup guide
├── 📄 PCA_GUIDE.md               # Detailed PCA concepts
├── 📄 FILE_STRUCTURE.md          # This file
│
├── 🐍 main.py                    # Main analysis script
├── 🐍 data_utils.py              # Utility functions
├── 🐍 config.py                  # Configuration settings
├── 🐍 verify_setup.py            # Setup verification
│
├── 📓 PCA_Analysis.ipynb         # Jupyter notebook
│
├── 📋 requirements.txt           # Python dependencies
├── 📋 .gitignore                 # Git ignore rules
│
├── 📂 data/                      # Data directory
│   └── lung-cancer.data          # Dataset (auto-downloaded)
│
└── 📂 outputs/                   # Output directory
    ├── pca_analysis_results.png  # Visualization
    ├── pca_results.csv           # Transformed data
    └── pca_loadings.csv          # Component loadings
```

---

## 📄 Documentation Files

### 1. README.md (⭐ START HERE)
**Purpose**: Complete project documentation

**Contents**:
- Project overview
- PCA explanation and concepts
- Installation instructions
- Usage guide
- Output file descriptions
- Learning outcomes
- References and resources
- FAQ section

**When to read**: First thing! When you want full understanding.

**Size**: ~8 KB | **Reading time**: 15-20 minutes

---

### 2. QUICKSTART.md
**Purpose**: Fast setup and running guide

**Contents**:
- 5-minute setup
- How to run analysis
- Understanding outputs
- Customization tips
- Troubleshooting
- Quick tips

**When to read**: When you want to get started quickly.

**Size**: ~6 KB | **Reading time**: 5-10 minutes

---

### 3. PCA_GUIDE.md (⭐ RECOMMENDED FOR LEARNING)
**Purpose**: Deep dive into PCA concepts and mathematics

**Contents**:
- Core PCA concepts
- Mathematical foundation
- Step-by-step process with examples
- Why feature scaling matters
- How to interpret results
- Practical tips and tricks
- Common pitfalls
- Summary checklist

**When to read**: When you want to understand PCA deeply.

**Size**: ~12 KB | **Reading time**: 30-40 minutes

---

### 4. FILE_STRUCTURE.md
**Purpose**: This file - describes all project files

**Contents**:
- Directory layout
- File descriptions
- File purposes and contents
- When to use each file

**When to read**: When navigating the project.

**Size**: ~8 KB | **Reading time**: 10 minutes

---

## 🐍 Python Scripts

### 1. main.py (⭐ THE MAIN SCRIPT)
**Purpose**: Complete PCA analysis pipeline

**What it does**:
1. Loads UCI Lung Cancer dataset
2. Performs exploratory data analysis (EDA)
3. Cleans data and handles missing values
4. Separates features and target
5. **Scales features** (StandardScaler)
6. Applies PCA transformation
7. Analyzes explained variance
8. Calculates component loadings
9. Analyzes correlation with target
10. Creates visualizations
11. Generates summary statistics
12. Saves results to CSV

**Key functions**:
- Data loading and cleaning
- Feature scaling
- PCA transformation
- Variance analysis
- Visualization generation
- Results saving

**How to run**:
```bash
python main.py
```

**Outputs**:
- Console output (detailed analysis)
- `pca_analysis_results.png` (4 subplots)
- `pca_results.csv` (transformed data)

**Size**: ~280 KB | **Execution time**: 5-10 seconds

**Customization points**:
- Line 180: `n_components = 2` - Change number of components
- Around line 100: Modify dataset URL
- Around line 300-400: Adjust visualization settings

---

### 2. data_utils.py
**Purpose**: Reusable data processing utility functions

**Functions included**:

| Function | Purpose |
|----------|---------|
| `load_lung_cancer_data()` | Downloads dataset from URL |
| `clean_data()` | Handles missing values, converts types |
| `separate_variables()` | Splits X and y |
| `scale_features()` | Applies StandardScaler |
| `print_data_summary()` | Prints comprehensive statistics |
| `get_feature_correlations()` | Calculates feature-target correlations |
| `display_memory_usage()` | Shows memory consumption |

**When to use**:
- When creating your own analysis scripts
- For modular, reusable code
- When building data pipelines

**Example usage**:
```python
from data_utils import load_lung_cancer_data, clean_data

df = load_lung_cancer_data()
df_clean = clean_data(df)
```

**Size**: ~5 KB | **Functions**: 7

---

### 3. config.py
**Purpose**: Centralized configuration settings

**Configuration sections**:

| Section | Purpose |
|---------|---------|
| DATA SETTINGS | Dataset URL, column names |
| PCA SETTINGS | Number of components, variance threshold |
| VISUALIZATION | Figure size, DPI, colors, fonts |
| FILE PATHS | Output directories and filenames |
| PREPROCESSING | Scaling method, missing value handling |
| ANALYSIS | Verbose mode, top N features |
| ML SETTINGS | Thresholds, test/train split |
| LOGGING | Log levels and output |

**When to use**:
- Before running analysis
- To adjust parameters in one place
- For reproducibility across runs

**Example**:
```python
from config import N_COMPONENTS_VISUALIZATION, OUTPUT_DIR

print(f"Using {N_COMPONENTS_VISUALIZATION} components")
print(f"Output to: {OUTPUT_DIR}")
```

**Size**: ~3 KB | **Settings**: 30+

---

### 4. verify_setup.py
**Purpose**: Test installation and setup

**What it checks**:
- Python version
- Required packages (numpy, pandas, sklearn, etc.)
- Optional packages (jupyter, ipython)
- Basic PCA functionality

**How to run**:
```bash
python verify_setup.py
```

**Output example**:
```
✅ numpy                 - OK (version: 1.24.3)
✅ pandas                - OK (version: 2.0.3)
✅ scikit-learn          - OK (version: 1.3.0)
...
✅ ALL CHECKS PASSED
```

**Use when**:
- First time setting up
- Troubleshooting installation issues
- Verifying dependencies

**Size**: ~3 KB | **Functions**: 3

---

## 📓 Jupyter Notebook

### PCA_Analysis.ipynb (⭐ INTERACTIVE LEARNING)
**Purpose**: Step-by-step interactive PCA analysis

**Format**:
- Jupyter notebook (.ipynb)
- Mix of code and markdown cells
- Visualizations embedded
- Can be run cell-by-cell

**Contents** (15 parts):
1. Introduction and objectives
2. Import libraries
3. Load data
4. Exploratory data analysis
5. Data cleaning
6. Variable separation
7. Feature scaling (with before/after)
8. Full PCA with variance analysis
9. Scree plot visualization
10. Apply PCA with selected components
11. Component loadings analysis
12. Loadings visualization
13. PCA projection plot
14. Correlation analysis
15. Summary and conclusions

**How to run**:
```bash
# Install Jupyter if not already
pip install jupyter

# Start Jupyter
jupyter notebook

# Open PCA_Analysis.ipynb
# Click "Run All" or run cells individually
```

**Advantages over main.py**:
- ✅ See results immediately
- ✅ Run individual sections
- ✅ Modify and experiment easily
- ✅ Embedded visualizations
- ✅ Educational markdown explanations
- ✅ Better for learning

**Size**: ~50 KB | **Cells**: ~30

**Customization**:
- Each cell can be modified independently
- Add new cells for experiments
- Change parameters and re-run

---

## 📋 Configuration Files

### requirements.txt
**Purpose**: List all Python package dependencies

**Contents**:
```
numpy==1.24.3
pandas==2.0.3
scikit-learn==1.3.0
matplotlib==3.7.2
seaborn==0.12.2
scipy==1.11.2
```

**Why it matters**:
- Ensures consistent environment
- Easy installation for others
- Version compatibility

**How to use**:
```bash
pip install -r requirements.txt
```

**Package purposes**:

| Package | Purpose |
|---------|---------|
| numpy | Numerical computing |
| pandas | Data manipulation |
| scikit-learn | Machine learning |
| matplotlib | Basic plotting |
| seaborn | Statistical visualization |
| scipy | Scientific computing |

**Size**: ~100 bytes

---

### .gitignore
**Purpose**: Exclude unnecessary files from Git

**What's ignored**:
- Python cache (`__pycache__/`)
- Virtual environments (`venv/`, `env/`)
- IDE files (`.vscode/`, `.idea/`)
- Jupyter checkpoints (`.ipynb_checkpoints/`)
- Data and output files (`*.csv`, `*.png`)
- OS files (`Thumbs.db`, `.DS_Store`)
- Temporary files (`*.log`, `*.tmp`)

**Why it matters**:
- Keeps repository clean
- Prevents large files from uploading
- Maintains focus on source code

**Size**: ~1 KB

---

## 📂 Data Directory

### data/
**Purpose**: Store datasets (created on first run)

**Contents after first run**:
```
data/
└── lung-cancer.data    # Downloaded dataset
```

**About the dataset**:
- Source: UCI Machine Learning Repository
- Size: ~5 KB
- Records: 32 patients
- Features: 14 medical attributes
- Target: Cancer/No Cancer

**Note**: Auto-downloaded from URL, can also be placed manually

---

## 📂 Outputs Directory

### outputs/
**Purpose**: Store analysis results and visualizations

**Generated files**:

#### pca_analysis_results.png
- **Type**: PNG image
- **Contents**: 4 subplots
  1. Scree plot (cumulative variance)
  2. PCA projection (PC1 vs PC2)
  3. Component loadings (bar chart)
  4. Explained variance (bar chart)
- **Size**: ~100-300 KB
- **DPI**: 300 (high quality)
- **Use**: Report, presentation, documentation

#### pca_results.csv
- **Type**: CSV file
- **Columns**:
  - PC1, PC2, ... (Principal components)
  - Class (Target variable)
- **Rows**: One per sample
- **Size**: ~1-2 KB
- **Use**: Further analysis, modeling, export

#### pca_loadings.csv
- **Type**: CSV file (if generated)
- **Rows**: Original features
- **Columns**: PC1, PC2, ...
- **Contents**: Loading values
- **Use**: Understanding feature importance

---

## 🔄 Typical Workflow

### For First-Time Users
```
1. Read QUICKSTART.md (5 min)
   ↓
2. Run verify_setup.py (1 min)
   ↓
3. Run main.py (5 min)
   ↓
4. Examine outputs (5 min)
   ↓
5. Read README.md (15 min)
```

### For Learning
```
1. Read PCA_GUIDE.md (40 min)
   ↓
2. Run PCA_Analysis.ipynb (30 min)
   ↓
3. Modify notebook (30 min)
   ↓
4. Read source code (20 min)
```

### For Production Use
```
1. Run main.py (5 min)
   ↓
2. Examine results (10 min)
   ↓
3. Integrate into pipeline (varies)
   ↓
4. Test with your data (varies)
```

---

## 📊 File Size Summary

| File | Type | Size | Purpose |
|------|------|------|---------|
| main.py | Python | 13 KB | Main analysis |
| PCA_Analysis.ipynb | Notebook | 50 KB | Interactive learning |
| README.md | Markdown | 8 KB | Full documentation |
| PCA_GUIDE.md | Markdown | 12 KB | Concept guide |
| QUICKSTART.md | Markdown | 6 KB | Quick reference |
| data_utils.py | Python | 5 KB | Utilities |
| config.py | Python | 3 KB | Settings |
| verify_setup.py | Python | 3 KB | Verification |
| requirements.txt | Text | 0.1 KB | Dependencies |
| .gitignore | Text | 1 KB | Git rules |

**Total**: ~100 KB (excluding outputs and data)

---

## 🔧 Customization Points

### Quick Customizations

**Number of components**:
- File: `main.py`
- Line: ~180
- Change: `n_components = 2`

**Variance threshold**:
- File: `config.py`
- Variable: `VARIANCE_THRESHOLD`
- Change: `0.95` to desired value

**Output directory**:
- File: `config.py`
- Variable: `OUTPUT_DIR`
- Change: `'./outputs/'` to desired path

**Dataset URL**:
- File: `config.py` or `data_utils.py`
- Variable: `DATASET_URL`
- Change: `https://...` to new URL

### Advanced Customizations

**Add new analysis**:
- Create new function in `data_utils.py`
- Call from `main.py`
- Use existing infrastructure

**Different dataset**:
- Modify `load_lung_cancer_data()` in `data_utils.py`
- Update column names in `config.py`
- Adjust data cleaning if needed

---

## 📚 Learning Resources by File

| Goal | Primary File | Secondary Files |
|------|---|---|
| Quick start | QUICKSTART.md | verify_setup.py |
| Run analysis | main.py | requirements.txt |
| Learn PCA | PCA_GUIDE.md | README.md |
| Interactive learning | PCA_Analysis.ipynb | PCA_GUIDE.md |
| Understand code | main.py | data_utils.py |
| Customize settings | config.py | main.py |
| Verify installation | verify_setup.py | requirements.txt |
| Understand outputs | README.md | PCA_GUIDE.md |

---

## 🎯 File Dependencies

```
main.py
  ├── Imports: numpy, pandas, sklearn, matplotlib
  ├── Downloads from: URL (UCI repository)
  ├── Uses: config.py (optional)
  └── Generates: PNG, CSV files

PCA_Analysis.ipynb
  ├── Imports: numpy, pandas, sklearn, matplotlib
  ├── Downloads from: URL (UCI repository)
  └── Generates: Embedded visualizations

data_utils.py
  ├── Imports: numpy, pandas, sklearn
  └── Used by: main.py (optional)

config.py
  ├── Imports: None (pure config)
  └── Used by: main.py (optional)

verify_setup.py
  ├── Imports: sys, importlib
  ├── Checks: All dependencies
  └── Runs: Independently
```

---

## ✅ Checklist for GitHub

Before pushing to GitHub:

- [ ] All Python files formatted correctly
- [ ] No hardcoded paths (use config.py)
- [ ] requirements.txt includes all packages
- [ ] .gitignore properly configured
- [ ] README.md is comprehensive
- [ ] File structure is clear
- [ ] No large files tracked (>100MB)
- [ ] All documentation is up-to-date
- [ ] Example output files included (optional)

---

**This file was last updated: September 2024**

For questions about any file, refer to the file's comments or the README.md.

# Video Games Recommendation System

An end-to-end exploratory data analysis and recommendation-system project built around a global video-game sales dataset. The project combines data cleaning, visualization, feature engineering, unsupervised learning, recommendation experiments, and an interactive Dash interface for exploring the results.

The main implementation is contained in [`TUT2_TDIA_112779.123557.123554.ipynb`](./TUT2_TDIA_112779.123557.123554.ipynb), supported by the dataset [`video_games_sales.csv`](./video_games_sales.csv).

## Project overview

The notebook investigates historical video-game sales across platforms, genres, publishers, and regions. It then transforms those observations into features that can be used for exploratory analysis, anomaly detection, clustering, association-rule mining, and game-similarity recommendations.

The workflow includes:

1. Dataset inspection and schema documentation.
2. Data cleaning and missing-value analysis.
3. Exploratory analysis of sales, genres, platforms, publishers, and release periods.
4. Feature engineering for decades, dominant sales regions, franchises, and regional success.
5. Outlier detection and dimensionality-reduction experiments.
6. Clustering and self-organizing-map analysis.
7. Association-rule mining for discovering relationships between games or game attributes.
8. Content-based similarity using text representations and cosine similarity.
9. Recommendation experiments and comparison of generated recommendations.
10. Interactive visual exploration through Plotly, widgets, and Dash components.

## Dataset

The included `video_games_sales.csv` file contains **16,598 records** and the following original variables:

| Column | Description |
| --- | --- |
| `rank` | Global sales ranking. |
| `name` | Game title. |
| `platform` | Platform on which the game was released. |
| `year` | Release year. |
| `genre` | Game genre. |
| `publisher` | Publishing company. |
| `na_sales` | Sales in North America, in millions of copies. |
| `eu_sales` | Sales in Europe, in millions of copies. |
| `jp_sales` | Sales in Japan, in millions of copies. |
| `other_sales` | Sales in other regions, in millions of copies. |
| `global_sales` | Total global sales, in millions of copies. |

The dataset contains 12 genres and 31 platforms. The notebook reports 271 missing release years and 58 missing publishers before preprocessing.

The dataset is based on the [Video Game Sales dataset on Kaggle](https://www.kaggle.com/datasets/ulrikthygepedersen/video-games-sales/data). Please consult the source dataset's terms and attribution requirements when redistributing or reusing the data.

## Analysis performed

### Data preparation

The notebook:

- Loads the CSV data with pandas.
- Renames the original columns into Portuguese for part of the analysis.
- Inspects data types, dimensions, missing values, and unique-value counts.
- Imputes missing release years using the mean available year.
- Fills missing publishers using a region-based fallback derived from the sales distribution.
- Creates additional attributes, including release decade, dominant sales region, and a simplified franchise identifier.

The publisher imputation is a project-specific heuristic rather than a recovery of the original publisher. Results involving that field should therefore be interpreted with caution.

### Exploratory data analysis

The notebook examines the distribution of games across:

- Release years and decades.
- Platforms and console generations.
- Genres.
- Publishers.
- Regional and global sales.
- Regional differences in game success.

The visual analysis uses Matplotlib, Seaborn, and Plotly to produce charts and interactive views.

### Unsupervised-learning techniques

Several unsupervised-learning and pattern-discovery methods are explored, including:

- **Isolation Forest** and **Local Outlier Factor** for anomaly detection.
- **PCA** and **UMAP** for dimensionality reduction and visualization.
- **K-Means** and **DBSCAN** for clustering games or engineered observations.
- **Silhouette score** for assessing cluster separation where applicable.
- **Self-Organizing Maps**, implemented with `MiniSom`.
- **Apriori** and association rules through `mlxtend`.

### Recommendation approaches

The notebook develops recommendation experiments using multiple perspectives:

- **Content-based similarity:** game metadata is transformed into comparable feature representations and evaluated with cosine similarity.
- **Feature- and cluster-based recommendations:** games can be related through shared genres, platforms, franchises, regions, or discovered clusters.
- **Association-based recommendations:** frequent itemsets and association rules are used to identify related game attributes or titles.
- **Hybrid experimentation:** recommendations can combine multiple signals instead of depending on a single feature or algorithm.

Because the dataset is based on sales and metadata rather than explicit user ratings, the recommendations should be understood as similarity- and popularity-oriented suggestions, not as a fully personalized production recommender trained on user interactions.

## Repository structure

```text
.
├── LICENSE
├── README.md
├── TUT2_TDIA_112779.123557.123554.ipynb
└── video_games_sales.csv
```

## Requirements

The notebook imports or relies on the following Python packages:

- `pandas`
- `numpy`
- `matplotlib`
- `seaborn`
- `scikit-learn`
- `umap-learn`
- `plotly`
- `ipywidgets`
- `dash`
- `requests`
- `MiniSom`
- `mlxtend`
- `Unidecode`
- Jupyter Notebook or JupyterLab

The repository currently does not include a `requirements.txt` file, so dependencies must be installed manually or captured in a local environment file.

## Installation and usage

### 1. Clone the repository

```bash
git clone https://github.com/IlieIftime/Video-games-system-recommendation.git
cd Video-games-system-recommendation
```

### 2. Create a virtual environment

```bash
python -m venv .venv
```

Activate it on Linux/macOS:

```bash
source .venv/bin/activate
```

Activate it on Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

### 3. Install the dependencies

```bash
python -m pip install --upgrade pip
python -m pip install pandas numpy matplotlib seaborn scikit-learn umap-learn plotly ipywidgets dash requests minisom mlxtend Unidecode jupyterlab
```

### 4. Open the notebook

```bash
jupyter lab
```

Open `TUT2_TDIA_112779.123557.123554.ipynb` and execute the cells from top to bottom. Keep `video_games_sales.csv` in the repository root because the notebook loads it with a relative path:

```python
pd.read_csv("video_games_sales.csv")
```

For the most reproducible results, restart the kernel and use **Run All** rather than relying on the notebook's saved execution order.

## Dashboard

The notebook imports Dash and contains dashboard-related code for interactive exploration of the data, metrics, and recommendation outputs. To use it:

1. Install the Dash dependencies listed above.
2. Execute the notebook cells required to build the processed data and recommendation objects.
3. Execute the dashboard section.
4. Open the local URL printed by Dash in your browser.

The dashboard depends on the variables created earlier in the notebook, so running only the final dashboard cells in a fresh kernel may not be sufficient.

## Reproducibility notes and limitations

- The notebook is designed as an educational and analytical project rather than a packaged application.
- Some cells contain inline installation commands and interactive display code; behavior may vary between Jupyter, JupyterLab, and standard Python execution.
- The data represents historical sales, not current market performance or player preferences.
- There are no explicit user-rating or user-history records, which limits conventional collaborative-filtering evaluation.
- Missing release years are filled with a global mean, and missing publishers are assigned using a sales-region heuristic. These choices may influence downstream clusters and recommendations.
- The notebook contains exploratory experiments with several algorithms. Their outputs depend on preprocessing choices, thresholds, random initialization, and the order in which cells are executed.
- Exact model scores should be taken from the executed notebook outputs rather than assumed from the project description.
- Android and iOS are not represented among the platforms observed in the dataset.

## Authors

- Ilie Iftime
- Inês Cruz
- Sofia Quintino

## License

This project is released under the [MIT License](./LICENSE).

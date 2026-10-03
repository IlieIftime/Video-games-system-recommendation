# Video Games Recommendation — EDA, Recommender & Dashboard
## Description
Single Jupyter Notebook containing an Exploratory Data Analysis (EDA) study on video game data, the implementation of a recommendation system (collaborative filtering / content-based / hybrid), and an interactive dashboard built with Dash to explore data and recommendations.

## Repository contents
TUT2_TDIA_112779.123557.123554 — Main notebook (EDA, recommendation pipeline, evaluation, and inference examples; includes a section with the Dash dashboard code).
requirements.txt — notebook dependencies (optional).
data/ — folder to place data files (not included in the repository if the data is sensitive).

## Requirements
Python 3.8+
Virtual environment recommended (venv or conda)
Main libraries: `pandas`, `numpy`, `scikit-learn`, `lightfm` or `surprise` (optional), `plotly`, `dash`, `jupyter`

## Quickstart
1º Clone / open the repository
Place the file Proj_Final_VFINAL1.ipynb in a local folder.

Create and activate a virtual environment:

````bash
python -m venv .venv
# Linux / macOS
source .venv/bin/activate
# Windows
.venv\Scripts\activate

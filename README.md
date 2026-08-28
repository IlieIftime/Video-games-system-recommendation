# Video Games Recommendation — EDA, Recommender & Dashboard

**Descrição**  
Notebook Jupyter único que contém um estudo de **Exploratory Data Analysis (EDA)** sobre dados de videojogos, a implementação de um **sistema de recomendação** (filtragem colaborativa / conteúdo / híbrido) e um **dashboard interativo** construído com Dash para explorar dados e recomendações.

---

## Conteúdo do repositório
- `Proj_Final_VFINAL1.ipynb` — Notebook principal (EDA, pipeline de recomendação, avaliação e exemplos de inferência; inclui secção com código do dashboard Dash).
- `requirements.txt` — dependências do notebook (opcional).
- `data/` — pasta para colocar ficheiros de dados (não incluída no repositório se os dados forem sensíveis).

---

## Requisitos
- Python 3.8+  
- Recomenda‑se ambiente virtual (`venv` ou `conda`)  
- Principais bibliotecas: `pandas`, `numpy`, `scikit-learn`, `lightfm` ou `surprise` (opcional), `plotly`, `dash`, `jupyter`

---

## Quickstart

1. **Clonar / abrir o repositório**  
   Colocar o ficheiro `Proj_Final_VFINAL1.ipynb` numa pasta local.

2. **Criar e ativar ambiente virtual**
```bash
python -m venv .venv
# Linux / macOS
source .venv/bin/activate
# Windows
.venv\Scripts\activate

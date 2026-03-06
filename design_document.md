# Design Document: Steam Game Discovery Explorer

## 1. Repository Structure
The project is organized to clearly separate concerns (data processing, algorithm, visualization, and frontend):

```text
steam-game-explorer/
├─ app.py
├─ data.py
├─ embed.py
├─ retrieval.py
├─ viz.py
├─ clustering.py
├─ utils.py
├─ requirements.txt
├─ README.md
├─ data/
│  ├─ raw/
│  └─ processed/
├─ notebooks/
│  ├─ 01_data_audit.ipynb
│  └─ 02_embedding_tests.ipynb
└─ assets/
```

**Component Descriptions:**
- `app.py`: Streamlit main interface, user inputs, and page routing.
- `data.py`: Loads, cleans, and prepares the HuggingFace Steam dataset.
- `embed.py`: Builds the combined text string and generates embedding vectors.
- `retrieval.py`: Implements from-scratch cosine similarity and nearest neighbor search.
- `viz.py`: Handles 2D map projections and interactive charts (PCA/t-SNE).
- `clustering.py`: Contains K-means logic for game segmentation.
- `utils.py`: Contains shared helper functions used across modules.
- `requirements.txt`: Defines project dependencies (Streamlit, pandas, sentence-transformers, etc.).
- `README.md`: Setup instructions, project overview, and run commands.

## 2. Division of Labor
Our team consists of 5 members. The responsibilities are modularized to ensure everyone has a concrete deliverable:
- **Member 1 (Data Engineer)**: Responsible for `data.py` and `01_data_audit.ipynb`. Handles downloading, cleaning, and formatting the dataset, handling missing values, and testing.
- **Member 2 (Embedding & ML Pipelines)**: Responsible for `embed.py` and `02_embedding_tests.ipynb`. Manages text aggregation and the sentence-transformers pipeline.
- **Member 3 (Core Algorithm Coder)**: Responsible for `retrieval.py`. Implements the pure python mathematical functions (vector normalization, dot product, top-k sorting) without library reliance.
- **Member 4 (Frontend Developer)**: Responsible for `app.py`. Integrates retrieval outputs into the Streamlit UI, building search bars, and results display.
- **Member 5 (Data Viz & Extensions)**: Responsible for `viz.py` and `clustering.py`. Creates latent space map projections, EDA charts, and adds optional K-means features.

## 3. Stub Code & GitHub Repository
*(Note for submission: The above structure will be initialized in a public GitHub repository. It will contain empty placeholder `.py` files, a functional `requirements.txt` to instantiate the virtual environment, and a `README.md` detailing the project.)*

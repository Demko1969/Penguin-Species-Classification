# Penguin Species Classification

Classify penguins as Adélie, Chinstrap, or Gentoo using three Python notebooks from the Kaggle competition **ARE SD 2026 — Adélie, Chinstrap ou Gentoo ?** The notebooks are written in French and implement the classifiers using NumPy and pandas.

| Notebook | Approach | Prediction file |
| --- | --- | --- |
| [Naive Bayes](notebooks/naive-bayes.ipynb) | Explores categorical and Gaussian Naive Bayes. The final submission uses island and sex. | `outputs/submission.csv` |
| [Decision tree](notebooks/decision-tree.ipynb) | Builds an entropy-based tree on the numerical measurements. | `outputs/sub_arbre3.csv` |
| [k-nearest neighbors](notebooks/k-nearest-neighbors.ipynb) | Standardizes numerical measurements, explores neighbor counts, and predicts with 17 neighbors using the labeled training set. | `outputs/kppv3.csv` |

## Run locally

Python 3.13 was used to verify the notebooks. Download the competition files before running the notebooks.

1. Sign in to Kaggle and open the [competition’s Data tab](https://www.kaggle.com/competitions/are-sd-2026-adelie-chinstrap-ou-gentoo/data).
2. If Kaggle prompts you to join the competition, review its rules. Use **Download All** to download the archive.
3. Extract the archive into a `data/` directory at the repository root. The notebooks expect `data/train.csv` and `data/prev.csv`. The archive also includes `data/benchmark.csv`, the example submission.

From the repository root, run:

```bash
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
jupyter lab
```

Open a notebook in `notebooks/` and choose **Run → Run All Cells**. Each notebook runs independently and writes a CSV with the columns `Id` and `espece`, in the same ID order as the supplied prediction data.

To run all three from the command line:

```bash
jupyter nbconvert --to notebook --execute --output-dir=outputs notebooks/*.ipynb
```

## Data

- `data/train.csv` contains 1,000 labeled examples.
- `data/prev.csv` contains 500 rows to classify.
- `data/benchmark.csv` is the supplied example submission and defines the expected column format.

The CSV files are available from the competition and are excluded from Git. The notebooks include exploratory scores computed with different data splits or on training data, so those scores do not establish a comparable test-set ranking.

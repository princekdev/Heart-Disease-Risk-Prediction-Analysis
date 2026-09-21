# data/ — Dataset Folder

## No manual download required

The dataset is fetched **automatically** by the Jupyter Notebook using the official `ucimlrepo` Python package:

```python
from ucimlrepo import fetch_ucirepo
heart_dataset = fetch_ucirepo(id=45)   # UCI Heart Disease, Cleveland subset
```

- **Internet access** is required the first time. The package caches the data locally for subsequent runs.
- No file needs to be placed in this folder manually.

---

## Dataset details

| Property    | Value |
|---|---|
| Name        | Heart Disease (Cleveland Clinic Foundation) |
| UCI ID      | 45 |
| URL         | https://archive.ics.uci.edu/dataset/45/heart+disease |
| DOI         | https://doi.org/10.24432/C52P4X |
| Rows        | 303 |
| Features    | 13 (age, sex, cp, trestbps, chol, fbs, restecg, thalach, exang, oldpeak, slope, ca, thal) |
| Target      | `num` (0–4, binarized to 0/1 in the notebook) |
| Missing     | `ca`: 4 NaNs, `thal`: 2 NaNs (handled by median imputation) |
| License     | CC BY 4.0 |

---

## Attribution

Original data contributed by:
- Andras Janosi, M.D. — Hungarian Institute of Cardiology, Budapest
- William Steinbrunn, M.D. — University Hospital, Zurich
- Matthias Pfisterer, M.D. — University Hospital, Basel
- Robert Detrano, M.D., Ph.D. — V.A. Medical Center, Long Beach & Cleveland Clinic Foundation

Cite as: Janosi, A., Steinbrunn, W., Pfisterer, M., & Detrano, R. (1988). *Heart Disease*. UCI Machine Learning Repository. https://doi.org/10.24432/C52P4X

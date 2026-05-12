## Quick Start
- Download for Windows: <[link](https://nuss.nagoya-u.ac.jp/s/amRFeigroZjfx3C)>
- Tutorial in Colab : <[link](https://colab.research.google.com/github/tkz-linglab/DepCollex/blob/main/notebooks/DepCollex_tutorial.ipynb)>
  - Notebooks are primarily tested on Google Colab; local Jupyter environments may require extra setup and may not be supported.

## License
This project is licensed under the MIT License. See LICENSE.
This applies to the code in the Colab notebook and the distributed binaries, unless noted otherwise.

## Citation
If you use this project in academic work, please cite BOTH:
1) Koizumi, T. (2026a). DepCollex: A tool for extracting and analyzing dependency-based collocations in learner corpora. In R. Murao & M. Morita (Eds.), *Second language acquisition research and English education: Festschrift for Profassor Masatoshi Sugiura* (pp. 42–56). Kaitakusha. 
2) Koizumi, T. (2026b). *DepCollex* (v1.x.x). GitHub repository: https://github.com/tkz-linglab/DepCollex

## Quick start (download → unzip → run)

1) Download the latest **ZIP** from the download link.
2) Unzip it to a local folder.
3) Run the executables in the order below.

## Important
- All input `.txt` files must be **UTF-8**.
---
## Workflow (3 executables)

This ZIP contains three executables:

1) **PairExtractor**  
   Extracts dependency pairs from target texts (learner corpus) and outputs:
   - `pair_all.csv`
   - `frequencies_<TYPE>.csv` (5 files)

2) **ParsedDocCreator**  
   Parses the reference corpus (native-speaker corpus) and creates `.spacy` files
   (cached parse results for scoring).

3) **ScoreCalculator**  
   Uses `pair_all.csv` + `.spacy` files to compute reference frequencies and association scores
   (MI, t-score), and outputs:
   - `pair_all_scores.csv`

---

## Step 1: PairExtractor (target texts → pairs)
- Click **Input folder** and select the folder containing `.txt` files (UTF-8).  
  Subfolders are searched recursively.
- Click **Output folder**
- Click **Extract start**

Outputs:
- `pair_all.csv`
- `frequencies_ADJ_NOUN.csv`
- `frequencies_VERB_OBJ.csv`
- `frequencies_ADV_VERB.csv`
- `frequencies_VERB_ADV.csv`
- `frequencies_ADV_ADJ.csv`

---

## Step 2: ParsedDocCreator (reference corpus → `.spacy` cache)
- Click **Input folder** and select the reference corpus folder (`.txt`)
- Click **Output folder**
- Set **n-processes** (CPU cores; start with 1–2 and increase if stable)
- Run

Output:
- `<output>/spacy/*.spacy`

---

## Step 3: ScoreCalculator (`pair_all.csv` + `.spacy` → scores)
- Select `pair_all.csv` (from Step 1)
- Select the `spacy/` folder (from Step 2)
- Select **Output folder**
- Run

Output:
- `pair_all_scores.csv`

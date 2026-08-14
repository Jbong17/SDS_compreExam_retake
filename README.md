# SDS Exam Kit — start here

You don't write code from scratch in the exam. You find the matching pre-built cell, point it at the data, run it, and explain the output. That's the whole method.

## Open this first
**`notebooks/05_PRACTICE_start_here.ipynb`** — a gentle two-question dry run. Do it once and the pattern clicks.

## The five-move routine for every exam question
1. Read the question.
2. Open **`notebooks/00_SDS_EXAM_PLAYBOOK.ipynb`** and use its lookup table to find the matching notebook.
3. Copy the cell(s) into your exam answer.
4. Change one line — the data file path — and run (Shift+Enter).
5. Read the output; write a short explanation using the "What to report" notes under the cell.

## What each notebook is for
| Notebook | Use it when the question is... |
|---|---|
| `00_SDS_EXAM_PLAYBOOK` | your map — read the lookup table first |
| `01_streaming_critique_and_verifiers` | "critique/fix this answer" about sampling, Bloom, reservoir, HyperLogLog, running IQR |
| `02_lsh_similarity_spark` | LSH design critique, or "find the most similar document" |
| `03_link_analysis_spark` | "compute PageRank" / "hubbiness & authority (HITS)" / "advice to CEO" |
| `04_graph_mining_spark` | "Girvan-Newman" / "SimRank" / "clustering coefficient" |
| `05_PRACTICE_start_here` | **do this first to practice** |

## Where to run
- **Notebook 01 (critiques)** runs in plain Python — practice anywhere.
- **Notebooks 02, 03, 04 (Spark code)** need Spark — practice on **Jojie**.

## On exam day
Open a terminal on Jojie and run:
```
git clone <your-private-repo-url>
```
Then open `notebooks/00_SDS_EXAM_PLAYBOOK.ipynb` and work question by question.

## Practice data (already included)
- `data/pageviews_practice.csv` — a small clickstream (like the Wikipedia one), for PageRank/HITS/communities.
- `data/corpus/` — small text collection, for find_similar.

## The one rule that matters most
The exam asks for **specific algorithms** — if it says Girvan-Newman, do Girvan-Newman (notebook 04), not something easier. And **run every cell before you submit** — a cell that hasn't run is worth nothing. The practice notebook builds both habits.

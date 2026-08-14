# SDS Comprehensive Exam Kit — Apache Spark

Battle-tested notebooks for the Scalable Data Science comp. Every Spark cell was executed against a real Spark 3.5.3 runtime during build. Allowed in exam: Jojie + GitHub + Copilot. **No LLMs. Built-in Spark only (no GraphFrames / no Spark packages).**

## Before the exam
1. Push this folder to a **private GitHub repo**; on Jojie `git clone` it.
2. Start Spark (nb 01 helper + a smoke test) and skim `00_SDS_EXAM_PLAYBOOK.ipynb`.
3. Do `05_REHEARSAL_DRILL.ipynb` (timed) on the included practice data.

## Files
| File | Use for |
|---|---|
| `00_SDS_EXAM_PLAYBOOK.ipynb` | strategy, phrase→cell lookup, 3 reflexes, correctness details, gotchas, time budget |
| `01_streaming_critique_and_verifiers.ipynb` | **~40% of exam** — critique/fix LLM streaming answers + runnable verifiers (hash-sampling, Bloom, reservoir, HLL, running-IQR) |
| `02_lsh_similarity_spark.ipynb` | LSH S-curve param tables (1a critique) + `find_similar` in Spark (TF-IDF cosine) |
| `03_link_analysis_spark.ipynb` | PageRank (DataFrame, dangling-mass) + HITS (RDD, persist/checkpoint) + advice |
| `04_graph_mining_spark.ipynb` | top-N subsetting + Girvan-Newman (modularity) + SimRank + clustering coefficient (full graph) |
| `05_REHEARSAL_DRILL.ipynb` | timed practice run |
| `data/pageviews_practice.csv` | TSV clickstream (power-law graph, named hubs) — mirrors the exam's `pageviews.csv` |
| `data/corpus/` + `corpus_manifest.txt` | themed text corpus + answer key for `find_similar` |

## The three reflexes (from a past exam that passed)
1. **Subset-with-justification** for super-linear algorithms (GN O(VE), SimRank O(n²)): induce the top-N-by-degree core in Spark, state why, run the exact algorithm there. PageRank/HITS/clustering-coeff scale → full graph.
2. **Small corpus ⇒ exact cosine beats LSH — and say so.**
3. **Honest "worse" result still scores** (e.g. SimRank fragments more than GN — state it).

## The one rule
Every subproblem gets executed Spark code + output + an interpretation, and **the numbers in your prose must equal what the code printed.**

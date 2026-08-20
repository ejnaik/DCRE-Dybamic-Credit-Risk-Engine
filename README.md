# Dynamic Credit Risk: Fusing GNN Fraud Detection, RL, and XAI

Companion code for the paper "Dynamic Credit Risk: Fusing GNN-Based Fraud
Detection, Reinforcement Learning, and Explainable AI."

## Pipeline (run in order)

```
cd code
python3 generate_data.py     # synthetic transaction graph + credit panel
python3 gnn_fraud.py         # GraphSAGE + GAT fraud detectors
python3 baseline_fraud.py    # tabular-only Random Forest baseline
python3 train_rl.py          # DQN dynamic credit-decisioning policy
python3 xai_layer.py         # GNNExplainer + SHAP explanations
python3 make_figures.py      # remaining paper figures
```

## Directory structure

- `code/` — all pipeline scripts (see above)
- `data/` — generated datasets, trained model weights, and result JSON/CSV
  artifacts (already populated from the run reported in the paper)
- `figures/` — all PNG figures used in the paper (already generated)
- `paper/` — the assembled thesis-chapter paper
  - `build_docx.js` — Node/docx-js script that assembles the .docx from
    the results in `data/` and figures in `figures/`
  - `Dynamic_Credit_Risk_GNN_RL_XAI.docx` — the final paper

## Requirements

Python 3.11, PyTorch 2.13, PyTorch Geometric 2.8, scikit-learn, shap,
pandas, pyarrow, networkx, matplotlib. Node.js with the `docx` npm
package for `paper/build_docx.js`.

All scripts are seeded (seed=42) for reproducibility.

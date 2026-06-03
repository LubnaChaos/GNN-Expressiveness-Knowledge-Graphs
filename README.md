# GNN Expressiveness on Knowledge Graphs

How much does relation-type awareness matter in graph neural networks?
This project investigates that question by comparing three models on
the FB15k-237 knowledge graph benchmark using link prediction as the
evaluation task.

# What is being compared

 - **GCN** : treats all edges the same, regardless of relation type
 - **RGCN** : uses separate weights for each relation type during aggregation
 - **DistMult** : no graph structure at all, just learned embeddings

## What I found

RGCN clearly outperforms plain GCN (0.970 vs 0.894 AUC), which confirms
that knowing the relation type during message passing makes a real difference.
Interestingly, DistMult scored only 0.621 — well below both GNN models —
showing that graph structure itself is important and cannot be replaced
by embedding similarity alone.

## Files

- `GRL_miniproject.ipynb` : full experiment code, run top to bottom
- `results.json` : AUC and loss recorded per epoch for all three models
- `results_figure.pdf` : results chart included in the written report




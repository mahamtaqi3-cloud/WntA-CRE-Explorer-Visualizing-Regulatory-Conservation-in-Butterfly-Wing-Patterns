# WntA CRE Explorer

A small exploratory Python notebook that visualizes how regulatory DNA (cis-regulatory elements, or CREs) around the butterfly wing pattern gene *WntA* can be conserved across species, how a single regulatory change can affect many wing regions, and how a simple machine learning model could be used to prioritize regulatory elements for testing.

This is a learning and concept-demonstration project, not a research result.

## Background

Butterfly wing patterns are controlled in part by genes such as *WntA*. Whether and where a gene is active depends on nearby non-coding regulatory DNA, which works like a set of switches. This project explores three ideas about these switches:

1. Many regulatory elements are conserved across related species, but some lineages differ.
2. Changing one regulatory element can alter several parts of a wing pattern, and can make a pattern shrink or expand.
3. Features of regulatory elements (such as DNA accessibility, conservation, and distance from the gene) could be used to train a model that predicts the direction of an effect.

## What the notebook contains

| Section | What it shows | Data |
|---|---|---|
| Picture 1 | Share of lineage-specific regulatory elements in monarch vs. other nymphalid butterflies | Reference values from published research (the "other nymphalids" bar is a midpoint of a reported range) |
| Picture 2 | Heatmap of how deleting each regulatory element changes different wing regions (blue = pattern lost, red = pattern expanded) | Simulated |
| Picture 3 | Feature importance from a Random Forest trained to predict whether a deletion shrinks or expands a pattern | Simulated |

## Important note on data

Only Picture 1 uses values taken from published research. Pictures 2 and 3 use randomly generated data created to illustrate the ideas. The model in Picture 3 learns a rule that was built into the simulated data, so its results say nothing about real butterfly biology. The notebook demonstrates a workflow, not a finding.

## Requirements

- Python 3.9 or later
- numpy
- matplotlib
- scikit-learn

Install with:

```bash
pip install numpy matplotlib scikit-learn
```

## How to run

**In Google Colab:** upload `WntA_CRE_Explorer.ipynb`, then choose **Runtime > Run all**.

**Locally:** open the notebook in Jupyter and run the cells from top to bottom. A random seed is set, so the plots are the same on every run.

## Limitations

- Pictures 2 and 3 are simulated and not based on experimental results.
- The machine learning example uses only 200 simulated elements and three made-up features.
- The "other nymphalids" value in Picture 1 is a midpoint of a reported range, not a single measured number.

## Possible next steps

1. Replace simulated features with real chromatin accessibility (ATAC-seq) and chromatin interaction (Hi-C) features for each regulatory element.
2. Use experimentally observed wing pattern changes as labels.
3. Evaluate the model on regulatory elements it has not seen, to check it is not just memorizing.
4. Test sequence-based models (for example, convolutional neural networks) that do not depend on sequence alignment.
5. Validate top predictions experimentally with CRISPR deletions.
6. Use larger genomic datasets, since a few dozen elements is too small for reliable model training.

## Project structure

```
WntA_CRE_Explorer.ipynb   # the notebook
README.md                 # this file
```

## License

For educational use.

### Dataset description

The original data was collected from the [supplementary material](https://static-content.springer.com/esm/art%3A10.1038%2Fs41598-017-17081-y/MediaObjects/41598_2017_17081_MOESM2_ESM.xlsx) of [Spencer and Zhang](https://www.nature.com/articles/s41598-017-17081-y).
It represents a DMS set for Streptococcus pyogenes Cas9. While sequences for Cas9 are available from UniProt, e.g. [Q99ZW2](https://www.uniprot.org/uniprot/Q99ZW2), it appears that the wild type used by the authors of this study differs slightly from any sequence deposited in UniProt.
As such, the wildtype sequence is considered as the WT reported by the study, and not one deposited in databases like UniProt.

The selected measures from this manuscript were:
- Log2 Fold Change after Negative Selection
- Log2 Fold Change after Positive Selection


### Full dataset

The `positive_mutation_matrix.csv` and `negative_mutation_matrix.csv` are LxN matrices representing either the positive or negative selection score for each AA subsitution along the protein length (L).

### Tasks

Both tasks are regression tasks, one being the Log2 Fold change after positive selection, the other after negative selection. 
Train/Test splits are done on the [PI domain](https://pfam.xfam.org/family/PF16595), meaning: train sequences are those with mutations NOT in the PI domain, while test sequences are those with mutations in the PI domain.


All tasks are contained in the `tasks.zip` file. These are CSV with colums:

- `sequence`: the AA sequence. May contain special characters!
- `target`: the prediction target. This may be continuous (`regression`), or True/False (`binary`)
- `set`: either `train` or `test`, if the sequence should be used for training or testing your model!
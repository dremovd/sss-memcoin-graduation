# sss-memcoin-graduation
Repository for organizing the contest

## Main idea

We run the same solution twice:

1. **Full run** on the original test set.  
2. **Truncated run** on a shortened test set (≈60% excluded) containing only data up to a specific slot.

Non-leak features should remain identical for the overlapping cases; leak-based features will likely differ because they relied on the now-excluded future data.

## Running order

> Skip `Prepare_shorter_test.ipynb`—its output datasets are already provided.


1. **Full-test run**  
   - Execute your solution on the original test set.  
   - Just before or after producing predictions, export all feature columns (including `mint` ID) and save this dump.

2. **Truncated-test run**  
   - Fork your solution and replace the datasets and relevant directories in the code.  
   - Run again and save the second feature dump (it will have fewer rows).

3. **Compare features**  
   - Run `Compare_features.ipynb` on both dumps to identify features with differences.

## Datasetss produced by `Prepare_shorter_test.ipynb`

https://www.kaggle.com/datasets/dremovd/pump-fun-graduation-february-2025-shorter

https://www.kaggle.com/datasets/dremovd/pump-fun-api-solana-tokens-info-shorter


> The training data is unchanged; only the test set is shortened at a defined cutoff. See `Prepare-shorter-test.ipynb` for details.








# Task 1: Minimal labeled dataset and evaluation split

## Goal
Build the smallest useful dataset for the Genesis law `y = 2x + 1 + noise`, with examples that are easy to inspect by hand.

## Feature meaning
- `x`: one real-valued input feature
- `y`: the observed target value generated from the linear rule plus noise

## Tiny dataset
| split | x   | y    | explanation |
|------|-----|------|-------------|
| train | 0.0 | 1.0  | close to `2*0 + 1 = 1` |
| train | 1.0 | 3.2  | close to `2*1 + 1 = 3` |
| train | 2.0 | 4.9  | close to `2*2 + 1 = 5` |
| train | 3.0 | 7.1  | close to `2*3 + 1 = 7` |
| eval  | 4.0 | 8.8  | close to `2*4 + 1 = 9` |
| eval  | 5.0 | 11.3 | close to `2*5 + 1 = 11` |

## Schema notes
- `split`: identifies whether the row is used for fitting or checking
- `x`: input column for the model
- `y`: supervised label to predict
- `explanation`: optional human check against the noiseless law

## Why this dataset works
The training rows cover a short, ordered range of `x` values and show the linear pattern clearly. The evaluation rows are held out so we can check whether learned parameters generalize beyond the fit set.

## Why representation matters
Because the model is `y_hat = w*x + b`, the dataset must make both the input feature and numeric target explicit. Even this tiny table is enough to teach the first-principles idea that learning starts from concrete labeled examples.

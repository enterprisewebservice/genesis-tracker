# Task 14: Minimal labeled dataset and evaluation split

## Goal
Create the smallest useful supervised dataset for the Genesis law `y = 2x + 1 + noise`.

## Feature meaning
- `x`: one scalar input feature
- `y`: observed target value generated from the linear rule plus noise

## Tiny dataset
| split | x   | y    | explanation |
|------|-----|------|-------------|
| train | 0.0 | 1.1  | near `2*0 + 1 = 1` |
| train | 1.0 | 2.9  | near `2*1 + 1 = 3` |
| train | 2.0 | 5.2  | near `2*2 + 1 = 5` |
| train | 3.0 | 6.8  | near `2*3 + 1 = 7` |
| eval  | 4.0 | 9.1  | near `2*4 + 1 = 9` |
| eval  | 5.0 | 10.7 | near `2*5 + 1 = 11` |

## Schema notes
- `split`: marks whether a row is used for fitting or checking
- `x`: numeric model input
- `y`: numeric supervised label
- `explanation`: optional human-readable comparison to the noiseless law

## Why this is enough
The training rows show the linear pattern clearly, while the held-out evaluation rows test whether learned parameters generalize beyond the fit set. This is the core first-principles lesson: learning depends on explicit labeled examples and a clear mapping from inputs to targets.

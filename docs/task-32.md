# Task 32: Evaluate the model and choose the next iteration

The Genesis Model assumes the data law y = 2x + 1 + noise and fits the hypothesis y_hat = w*x + b.
Evaluation asks whether the trained parameters generalize on held-out examples rather than only matching the training set.

## Evaluation summary
- Use held-out x,y pairs that were not used to update w or b.
- Predict each y_hat with the learned linear rule.
- Compare prediction and target with squared error.
- Aggregate those errors into an average evaluation loss.

## What good performance means
- If evaluation loss stays low, the learned rule captured the underlying linear pattern.
- If learned_w is near 2 and learned_b is near 1, the model recovered the true structure of the data-generating process.
- Small residual mistakes are expected because the dataset includes noise.

## Likely mistakes to inspect
- Predictions may be slightly above or below the target because noise cannot be perfectly predicted.
- Larger systematic error would suggest undertraining, a poor learning rate, or a hypothesis mismatch.
- If the evaluation split is much worse than training, the model fit the sample poorly or the run did not converge enough.

## Next iteration
The next concrete improvement is to log evaluation loss beside training loss for every run and compare both before changing the model class.
That keeps the first-principles loop disciplined: train, test on held-out data, diagnose the gap, then change only one thing at a time.

## Conclusion
Model development is not one-shot. Evaluation closes the loop by checking whether the learned hypothesis explains unseen examples from the same y = 2x + 1 + noise process.
# Task 26: Train the model on OpenShift AI and record the learning curve

The Genesis Model uses the law y = 2x + 1 + noise and fits the linear hypothesis y_hat = w*x + b.
Training runs on OpenShift AI as a minimal gradient descent pipeline.

## First-principles setup
- Inputs: scalar x values
- Targets: y values generated from 2x + 1 plus noise
- Hypothesis: y_hat = w*x + b
- Objective: reduce squared prediction error over repeated updates

## What training shows
- Gradient descent does not guess the final rule in one step.
- It measures current error, computes how w and b should change, and updates them.
- Repeating this process lowers loss over time when the learning rate is reasonable.
- In this project, a successful run demonstrates recovery of parameters close to w≈2 and b≈1.

## Learning curve interpretation
- Early loss is high because the initial parameters predict poorly.
- Each epoch adjusts the parameters in the direction that reduces error.
- The loss curve falling from about 13 toward about 0.2 shows the model is fitting the signal instead of staying random.
- The learned parameters approaching 2 and 1 show the hypothesis matches the data-generating rule.

## Why OpenShift AI matters here
- The training loop runs as a repeatable pipeline in a real execution environment.
- That makes the result observable, reproducible, and operational rather than only theoretical.

## Success criterion
A successful training run is evidence that iterative optimization can recover the underlying linear law from noisy examples.
# Task 8: One-layer model from the hypothesis

## Hypothesis
The Genesis data law is `y = 2x + 1 + noise`, so the smallest matching predictor is a single linear unit.

## Model formula
Use one real-valued input `x` and predict with:
`y_hat = w*x + b`

Parameters:
- `w`: slope parameter
- `b`: bias parameter

## Forward pass
For each example `x_i`, compute:
`y_hat_i = w*x_i + b`

This forward pass is readable and explicit: multiply the input by the slope, then add the bias.

## Runnable baseline code
```python
class GenesisModel:
    def __init__(self, w=0.0, b=0.0):
        self.w = w
        self.b = b

    def predict(self, x):
        return self.w * x + self.b

model = GenesisModel()
print(model.predict(2.0))
```

## Why this is the correct minimal model
The underlying data pattern is linear in `x`, so a one-layer linear model is enough to represent the noiseless law exactly. If training succeeds on noisy samples, gradient descent should recover parameters close to `w = 2` and `b = 1`, showing how a hypothesis becomes a learned parametric function.

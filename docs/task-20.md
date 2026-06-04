# Task 20: One-layer model from the hypothesis

## Hypothesis
The data follow the law `y = 2x + 1 + noise`, so the simplest predictive model should map one scalar input to one scalar output with a line.

## Model formula
`ŷ = w*x + b`

- `x`: numeric input feature
- `w`: learnable slope parameter
- `b`: learnable bias parameter
- `ŷ`: predicted target

## Minimal runnable baseline
```python
# one-layer linear model
w = 0.0
b = 0.0

def predict(x):
    return w * x + b

example_x = 3.0
print(predict(example_x))
```

## Why this matches first principles
A hypothesis becomes a parameterized function by making the unknown parts explicit. Here, `w` and `b` are the only learnable quantities needed to express a straight-line rule.

## Why this is the right baseline
Because the underlying law is linear, a one-layer linear unit is the smallest model class that can represent the signal. Noise affects observed targets, but it does not change the core structure the model should learn.

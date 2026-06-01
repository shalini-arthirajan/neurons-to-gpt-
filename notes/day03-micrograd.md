# Day 03 — Automatic Differentiation & Building a Neural Network

### 1. Backpropagation Through an Entire Graph

Each operation only needs to know how to compute its local derivative.

By traversing the graph backwards and repeatedly applying the chain rule, gradients can be computed for every node automatically.

This is the key idea behind automatic differentiation.

---

### 2. Breaking Down Complex Operations

Operations such as `tanh` can be decomposed into simpler mathematical operations.

Even complex neural network computations are ultimately compositions of simple operations whose derivatives are easy to calculate.

---

### 3. Why `__radd__` and `__rmul__`?

Initially, operations only worked when both operands were `Value` objects.

Example:

```python
a + b
```

where both `a` and `b` are `Value`s.

However:

```python
2 + a
```

would fail because Python first tries to use the integer's addition method.

`__radd__` and `__rmul__` allow operations where a regular number appears on the left side.

Examples:

```python
2 + a
3 * a
```

This makes the `Value` class behave more naturally and feel like a regular number while still preserving the computational graph.

---

### 4. Micrograd vs PyTorch

Micrograd:
- Built for learning.
- Uses a tiny custom `Value` class.
- Implements automatic differentiation from scratch.
- Makes every step of backpropagation visible.

PyTorch:
- Production-grade deep learning framework.
- Uses optimized tensor operations.
- Handles automatic differentiation internally.
- Scales to large models and GPUs.

A useful realization:

```python
loss.backward()
```

in PyTorch is doing the same conceptual work as the backpropagation system built manually in Micrograd.

---

### 5. Building a Neural Network

A neural network can be built using layers of abstraction:

Value
↓
Neuron
↓
Layer
↓
Multi-Layer Perceptron (MLP)

Large neural networks are ultimately compositions of many simple mathematical operations.

---

### 6. Loss Functions

A loss function measures how wrong a model's predictions are.

Training aims to minimize this value.

Lower loss generally means the model is performing better on the task.

---

### 7. Parameters

Parameters are the values the network learns during training.

Examples:
- weights
- biases

Collecting all parameters allows them to be updated together during optimization.

---

### 8. Gradient Descent

Training follows a simple loop:

1. Perform a forward pass.
2. Compute the loss.
3. Run backpropagation.
4. Compute gradients.
5. Update parameters.
6. Repeat.

The gradients indicate which direction each parameter should move to reduce the loss.

---

### Local Derivatives

For each operation in a computational graph, we can calculate how sensitive the output is to each input.

#### Addition

c = a + b

Local derivatives:

dc/da = 1

dc/db = 1

This means a small change in either input produces the same change in the output.

Example:

If `a` increases by 0.001,

then `c` also increases by 0.001.

---

#### Multiplication

c = a × b

Local derivatives:

dc/da = b

dc/db = a

Unlike addition, the sensitivity of one input depends on the value of the other input.

Example:

If:

a = 2
b = 3

Then:

dc/da = 3

dc/db = 2

A small change in `a` affects the output 3 times as much, while a small change in `b` affects the output 2 times as much.

---

### Connection to Backpropagation

Backpropagation works by calculating these local derivatives for every operation in a computational graph and combining them using the chain rule.

A large neural network can therefore be viewed as many small derivative calculations stitched together.


### 1. Derivatives for sensitivity
a derivative helps us see
> "How much does the output change if I slightly change the input?"
which is how neural networks learn

---

### 2. Computational graphs aka Expression graphs
A mathematical expression can be represented as a graph
Each node stores:
- a value
- how it was created

---

### 3. The Value object 

Value class stores:
- the number itself "self.data"
- relationships to other values using the "(self,other)"
- the operation that created it
for computing gradients
---

### Why `__repr__`?
Makes `Value` objects readable when printed and helps with debugging.

without __repr__ , python would print the object's memory reference
example:  "<__main__.Value at 0x2591e4dd590>" 

with __repr__, python can print the information inside the object
example: "Value(data=-8.0)"


### Why `Value` instead of floats?

Floats only store numbers; `Value` objects also store the computational history like where it came from and using what operator needed to compute gradients.



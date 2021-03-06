## HingeEmbeddingCriterion ##


**Scala:**
``` scala
val m = HingeEmbeddingCriterion(margin = 1, sizeAverage = true)
```
**Python:**
```python
m = HingeEmbeddingCriterion(margin=1, size_average=True)
```


Creates a criterion that measures the loss given an input `x` which is a 1-dimensional vector and a label `y` (`1` or `-1`).
This is usually used for measuring whether two inputs are similar or dissimilar, e.g. using the L1 pairwise distance, and is typically used for learning nonlinear embeddings or semi-supervised learning.

```
                 ⎧ x_i,                  if y_i ==  1
loss(x, y) = 1/n ⎨
                 ⎩ max(0, margin - x_i), if y_i == -1
```



**Scala example:**
```scala
import com.intel.analytics.bigdl.utils.{T}
import com.intel.analytics.bigdl.tensor.Tensor
import com.intel.analytics.bigdl.nn._
import com.intel.analytics.bigdl.utils.{T}
import com.intel.analytics.bigdl.tensor.TensorNumericMath.TensorNumeric.NumericFloat

val loss = HingeEmbeddingCriterion(1, sizeAverage = false)
val input = Tensor(T(0.1f, 2.0f, 2.0f, 2.0f))
println("input: \n" + input)
println("ouput: ")

println("Target=1: " + loss.forward(input, Tensor(4, 1).fill(1f)))

println("Target=-1: " + loss.forward(input, Tensor(4, 1).fill(-1f)))
```

```
input: 
0.1
2.0
2.0
2.0
[com.intel.analytics.bigdl.tensor.DenseTensor of size 4]
ouput: 
Target=1: 6.1
Target=-1: 0.9

```

**Python example:**
```python
import numpy as np
from bigdl.nn.criterion import *
input = np.array([0.1, 2.0, 2.0, 2.0])
target = np.full(4, 1)
print("input: " )
print(input)
print("target: ")
print(target)
print("output: ")
print(HingeEmbeddingCriterion(1.0, size_average= False).forward(input, target))
print(HingeEmbeddingCriterion(1.0, size_average= False).forward(input, np.full(4, -1)))
```
```
input: 
[ 0.1  2.   2.   2. ]
target: 
[1 1 1 1]
output: 
creating: createHingeEmbeddingCriterion
6.1
creating: createHingeEmbeddingCriterion
0.9
```


## CAddTable ##

**Scala:**
```scala
val module = CAddTable(inplace = false)
```
**Python:**
```python
module = CAddTable(inplace=False)
```

CAddTable merges the input tensors in the input table by element-wise adding. The input table is actually an array of tensor with same size.

**Scala example:**
```scala
import com.intel.analytics.bigdl.tensor.TensorNumericMath.TensorNumeric.NumericFloat
import com.intel.analytics.bigdl.nn._
import com.intel.analytics.bigdl.tensor._

val mlp = Sequential()
mlp.add(ConcatTable().add(Identity()).add(Identity()))
mlp.add(CAddTable())

println(mlp.forward(Tensor.range(1, 3, 1)))
```
Output is
```
com.intel.analytics.bigdl.nn.abstractnn.Activity =
2.0
4.0
6.0
[com.intel.analytics.bigdl.tensor.DenseTensor of size 3]
```

**Python example:**
```python
from bigdl.nn.layer import *
import numpy as np

mlp = Sequential()
mlp.add(ConcatTable().add(Identity()).add(Identity()))
mlp.add(CAddTable())

print(mlp.forward(np.arange(1, 4, 1)))
```
Output is
```
[array([ 2.,  4.,  6.], dtype=float32)]
```

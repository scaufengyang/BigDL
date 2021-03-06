## Identity ##

**Scala:**
```scala
val identity = Identity()
```
**Python:**
```python
identity = Identity()
```

Identity just return input as the output which is useful in same parallel container to get an origin input

**Scala example:**
```scala
import com.intel.analytics.bigdl.tensor.TensorNumericMath.TensorNumeric.NumericFloat
import com.intel.analytics.bigdl.nn._
import com.intel.analytics.bigdl.tensor._
val identity = Identity()

val input = Tensor(3, 3).rand()
> print(input)
0.043098174	0.1035049	0.7522675	
0.9999951	0.794151	0.18344955	
0.9419861	0.02398399	0.6228095	
[com.intel.analytics.bigdl.tensor.DenseTensor$mcF$sp of size 3x3]

> print(identity.forward(input))
0.043098174	0.1035049	0.7522675	
0.9999951	0.794151	0.18344955	
0.9419861	0.02398399	0.6228095	
[com.intel.analytics.bigdl.tensor.DenseTensor$mcF$sp of size 3x3]


```

**Python example:**
```python
from bigdl.nn.layer import *
identity = Identity()
>  identity.forward(np.array([[1, 2, 3], [4, 5, 6]]))
[array([[ 1.,  2.,  3.],
       [ 4.,  5.,  6.]], dtype=float32)]
       
```



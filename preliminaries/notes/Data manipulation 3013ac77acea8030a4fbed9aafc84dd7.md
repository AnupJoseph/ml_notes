# Data manipulation

Notes: Statistics (https://www.notion.so/Statistics-3013ac77acea80508243fc21eed36966?pvs=21)

## Broadcasting

Broadcasting works according to the following two-step procedure: 

1. expand one or both arrays by copying elements along axes with length 1 so that after this transformation, the two tensors have the same shape
2. perform an elementwise operation on the resulting arrays.

## Memory

Running operations can cause new memory to be allocated to host results. 

This might be undesirable for two reasons. First, we do not want to run around allocating memory unnecessarily all the time. In machine learning, we often have hundreds of megabytes of parameters and update all of them multiple times per second. Whenever possible, we want to perform these updates *in place*. Second, we might point at the same parameters from multiple variables. If we do not update in place, we must be careful to update all of these references, lest we spring a memory leak or inadvertently refer to stale parameters.

Fortunately, performing in-place operations is easy. We can assign the result of an operation to a previously allocated array `Y` by using slice notation: `Y[:] = <expression>`.
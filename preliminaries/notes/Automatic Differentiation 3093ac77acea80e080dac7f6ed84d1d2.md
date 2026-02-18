# Automatic Differentiation

Notebook: Preliminaries (https://www.notion.so/Preliminaries-3013ac77acea804b9342fe18cf354e45?pvs=21)
Archived: No

## **Backward for Non-Scalar Variables**

When `y` is a vector, the most natural representation of the derivative of `y` with respect to a vector `x` is a matrix called the *Jacobian* that contains the partial derivatives of each component of `y` with respect to each component of `x`.

## Basics

1. attach gradients to those variables with respect to which we desire derivatives
2. record the computation of the target value
3. execute the backpropagation function
4. access the resulting gradient.
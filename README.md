Download link :https://programming.engineering/product/math-6001-nonlinear-optimization-in-machine-learning-final-project/

# MATH-6001.-Nonlinear-Optimization-in-Machine-Learning.-Final-Project.
MATH 6001. Nonlinear Optimization in Machine Learning. Final Project.
There are 8 problems that are marked with underlines. Each problem is worth 5 points, and the total is 40 points.

Part 1. Consider the heavy ball method iteration at dimension 2

xk+1 = xk rf(xk) + (xk xk 1) ;

(0.1)

where x 1 = x0 2 R2 and ; > 0. Let the function f be quadratic of the form

1

T

T

f(x) =

x

Qx

b

x + c ;

(0.2)

2

such that the Hessian matrix Q is a 2 2 positive de nite matrix with the two eigenvalues

0 < m = 21 = L < 1 ;

(0.3)

and b 2 R2 and c 2 R. Set

p

p

4

L

m

=

(p

+ p

)2

; =

p

p

:

(0.4)

L

L +

m

m

Following the \spectral method” proof of the convergence of Nesterov’s scheme in x4.1 of Chapter 4 in the Lecture Notes, we can obtain a linear convergence rate on the

convex quadratic f(x) in (0.2). We split the proof into 5 steps.

Problem 1. Write the algorithm as a linear recursion wk+1 choice of matrix T and state variables wk.

Problem 2. Use a transformation to express T as a block{diagonal matrix, with 2 2 blocks Ti on the diagonals, where each Ti depends on a single eigenvalue i of Q.

Problem 3. Find the eigenvalues i;1, i;2 of each Ti as a function of i, and .

Problem 4. Show that for the given values of and , these eigenvalues are all complex.

p

Problem 5

. Show that in fact j i;1j = j i;2j =for all i = 1; 2, so that (T )

j

i;2j

) = p

1=2, where the condition number =

L

max max(

;

1

>> 1.

m

i=1;2

j

i;1j


1 n

P

Part 2. Consider the standard nite{sum objective function f(x) = n i=1 fi(x),

which is commonly seen in machine learning. Let us further assume that the component functions fi are further associated with Gaussian noise model, that is

[rfi(x)]j = [rf(x)]j + “ij ; for all i = 1; 2:::; n and j = 1; 2; :::; d ;

(0.5)

where “ij N (0; 2) is a Gaussian distribution with mean 0 and variance 2.

Problem 6. Show that when we estimate the gradient using a randomly sampled minibatch S f1; 2; :::; ng, that is,

g =

1

X

rfi(x) ;

(0.6)

jSj

i

2S

then we have

d

Ekg r

f(x)k2

=

2 :

jSj

Problem 7. Following Problem 6, show that

E(kgk2) = krf(x)k2 + jSjd 2 :

Problem 8. Consider a minibatch strategy for the additive Gaussian noise model, where the gradient estimate is given by

1

s

Xj

g(x; 1; 2; :::; s) = rf(x) + s

j ;

=1

where each j is i.i.d with distribution N (0; 2I), that is a multivariate normal distri-bution with mean 0 and covariance matrix 2I, and s 1. Show that

E 1; 2;:::; s (kg(x; 1; 2; :::; s)k2) = krf(x)k2 + ds 2 :

2

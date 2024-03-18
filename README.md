[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/8KYthzwp)
# Recurrent Recurrences

Give big $\Theta$ bounds for the following recurrence relations.

1.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

Answer 1:

$T(n) = T(\frac {n} {13}) + 5$

$= T(\frac {n} {169}) + 10$

$= T(\frac {n} {2197}) + 15$

So, $= T(\frac {n} {13^i}) + 5^i$ and $i = log n$.

$= T(1) + 5(logn)$

$= \Theta (logn)$

---------------------------------------------------------------------------

2.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 5 & n > 1
    \end{cases}
$$

Answer 2:

$T(n) = 13T(\frac {n} {13}) + 5$

$= 13(13T(\frac {n} {169}) + 5) + 5$

$= 169T(\frac {n} {169}) + 13(5) + 5$

$= 169(13T(\frac {n} {2197}) + 5) + 13(5) + 5$

$= 2197T(\frac {n} {2197}) + 169(5) + 13(5) + 5$

So, $= 13^i \cdot T(\frac {n} {13^i}) + 5 \cdot \sum 13^k$ and $i = log_{13} n$.

$= 13$ ^ $(log_{13} n) \cdot T(1) + 5 \cdot \sum 13^k$

$= n + 5 \cdot \sum 13^k$

$= \Theta (n)$

---------------------------------------------------------------------------

3.
$$ T(n) =
    \begin{cases}
        1 & n \leq 1\\
        13 T\left(\frac{n}{13}\right) + 2n & n > 1
    \end{cases}
$$

Answer 3:

$T(n) = 13T(\frac {n} {13}) + 2n$

$= 13(13T(\frac {n} {169}) + 2(\frac {n} {13})) + 2n$

$= 169T(\frac {n} {169}) + 4n$

$= 169(13T(\frac {n} {2197}) + 2(\frac {n} {169})) + 4n$

$= 2197T(\frac {n} {2197}) + 6n$

So, $= 13^i \cdot T(\frac {n} {13^i}) + 2 \cdot i \cdot n$ and $i = log_{13} n$.

$= 13$ ^ $(log_{13} n) \cdot T(1) \cdot 2(log_{13} n)n$

$= n \cdot 2(log_{13} n)n$

$= \Theta (n log n)$

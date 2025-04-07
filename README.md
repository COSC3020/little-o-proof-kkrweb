# Little-o

In addition to the big-O, big-$\Omega$, and big-$\Theta$ notation that
we covered at the beginning of this class, a few other notations are sometimes
used in asymptotic analysis.  For example, "little-$o$" notation.

Prove (i.e.\ give a formal mathematical proof) that $f(n)\in o(g(n))$ implies
that $f(n)\in O(g(n))$.

Hint: The proof will be *very* short and *very* easy. You can start by
identifying the differences between the definitions of O and o.

I have started with the formal definition of $o$ below. Add your answer to this
markdown file. [This
page](https://docs.github.com/en/get-started/writing-on-github/working-with-advanced-formatting/writing-mathematical-expressions)
might help with the notation for mathematical expressions.

$f(n)\in o(g(n)) \iff \forall c>0, \exists n_0, \forall n\ge n_0: f(n) < c g(n)$


//


Name: Kane Kriz

Date Started: 13 Feb 2025

Last Edited: 7 April 2025

Feedback Request 1 Date: X

//


Response, Proof:

Definition of little o - $f(n) \in o(g(n)) \iff \forall c > 0, \exists n_0, \forall n \geq n_0 : f(n) < c * g(n)$.

Definition of big O - $f(n) \in O(g(n)) \iff \exists c > 0, \exists n_0, \forall n \geq n_0 : f(n) \leq c * g(n)$


(Start of actual proof below)


Theorem: $f(n) \in o(g(n)) \implies f(n) \in O(g(n))$.


Proof:


$f(n) \in o(g(n))$ was provided within the exercise description to be the theorem we are after.
We can start by assuming the theorem is given and work on from that point.

Given - $f(n) \in o(g(n))$

Per the definition of little o notation, this means:
$\forall c > 0, \exists n_c \in \mathbb{N}, \forall n \geq n_c : |f(n)| < c|g(n)|$.

To show $f(n) \in O(g(n))$, we must establish that:
$\exists C > 0, \exists n_0 \in \mathbb{N}, \forall n \geq n_0 : |f(n)| \leq C|g(n)|$.

We now set constant $c = 1$ within the little o definition. 

There exists $n_1 \in \mathbb{N}$ such that for all $n \geq n_1$: $|f(n)| < 1 \cdot |g(n)|$.

By properties of real numbers, $|f(n)| < |g(n)|$ implies $|f(n)| \leq |g(n)|$ for all $n \geq n_1$.

Taking $C = 1$ and $n_0 = n_1$, we satisfy the big O definition:

$\exists C = 1 > 0, \exists n_0 = n_1, \forall n \geq n_0 : |f(n)| \leq C|g(n)|$.

The big O definition is satisfied through the following logical progression:

The big O definition is satisfied through reasoning away from the properties of the little o definition. 
Quantifier $\exists C>0$ is satisfied by the selection of $C=1$, which was made as it was positive.
Quantifier $\exists n_0$ is satisfied by taking $n_0 = n_1$, where $n_1$ is known to exist from the little o definition with $c=1$. 

The universal quantification $\forall n \geq n_0$ holds because the little o definition guarantees $|f(n)| < |g(n)|$ for all $n \geq n_1$, and consequently $|f(n)| \leq |g(n)|$ for these same values of $n$. 
This logical progression from the little o definition ensures all of the necessary quantifier requirements are met.

Therefore, $f(n) \in o(g(n)) \implies f(n) \in O(g(n))$.

QED


//


Plagiarism Acknowledgement: I certify that I have listed all sources used to complete this exercise, including the use of any Large Language Models. All of the work is my own, except where stated otherwise. I am aware that plagiarism carries severe penalties and that if plagiarism is suspected, charges may be filed against me without prior notice.


Citations:

https://www.stat.cmu.edu/~cshalizi/uADA/13/lectures/app-b.pdf

https://www.geeksforgeeks.org/difference-between-big-oh-big-omega-and-big-theta/

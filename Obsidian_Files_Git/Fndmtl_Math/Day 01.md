## <mark style="background: #FFB8EBA6;">Sets</mark>

>Def: A set is a collection of things 

* N natural numbers 0, 1, 2, ...、
* $Z$ the integers 0, 1,-1, 2, ...
* Q the rational numbers 
* R the real numbers 
* $\emptyset$  the empty set 
* $\in$ means 'is an <mark style="background: #BBFABBA6;">element</mark> of'
* $\ni$ means 'is not a element of'
---------
>Describing Sets

**In terms if their properties:

$\{n \in |   n\geq27 \}$

alternative: $\{ n \in Z : n^2 \leq n\}$

{1, 2, {3, 4}}

---
>Features 

* Set can be members of sets 

$\{\ \{1,2\}1,2\}$ has three elements 
$\{\{\{1,2\},1 \},2\}$ has two elemens
{} has zero elements

* *==A set doesn't have an order==

$\{1,2\}$ and $\{2, 1\}$ is the same set 

* Present only once
* $\{1, 1\}$ is the same as $\{1\}$
* Same if they have the same elements

* ==Present only once ==
* $\{1, 1\}$ has the same meaning as $\{1\}$ 
* 
## <mark style="background: #FF5582A6;">Subset</mark>

>Def: A subset of a set, X, means a set every element of which is also
an element of X. The empty set is a subset of every set.
	Symbolically, A $\subseteq$ B 
	$\forall x$ (x $\in$ A $\rightarrow$ x $\in$ B) 
>Syntax 
>If A is a subset of X we write A $\subseteq$ X.
>

###  <mark style="background: #FFB86CA6;">Power subset
</mark>

>>	Def: In set theory, a power set is the set of all subsets of a given set, including the empty set.

>>Syntax:
>>$\mathcal{P}(X)$
### <mark style="background: #FFB86CA6;">Proper subset</mark>

> Def: A proper subset of X is a set containing some but not all of the
elements of X. We can use A ⊂ X to mean A is a proper subset
of X; another notation is A ⊊ X. 
### <mark style="background: #FFB86CA6;">SuperSet</mark>

>Def:
>A is a superset of B, denoted A ⊇ B, if B ⊆ A, and we
say A is a proper superset of B, denoted A ⊃ B, if B ⊂ A.


>![[Pasted image 20230904222911.png]]

{2} {1} {0} {1}
{{2}, {1} {} {1}}

----------------

### <mark style="background: #FFB86CA6;">Cardinalities</mark>

>Def:
The cardinality of a set means the number of elements in it.
We write |X| for the cardinality of X.

NOTE: $|\emptyset| = 0$

A = {1, 2, 3}
|A| = 3

Some facts:

1. |A ∪ B| = |A| + |B| − |A ∩ B|
2. |A ∩ B| = |A| + |B| − |A ∪ B|
3. |A ⊕ B| = |A − B| + |B − A|
4. |A| = |U| − |A|
5. |A − B| = |A| − |A ∩ B|

### <mark style="background: #FFB86CA6;"> operations</mark> on Set

* Union A ∪ B contains all the elements of A together with all
those of B
* Intersection. A ∩ B contains the elements present both in A
and in B.
* Complement. The complement of A is everything in U
which is not in A.
*  Difference. A − B is the set containing everything in A
which is not in B. Also often denoted A \ B.
* Symmetric difference. A ⊕ B is the set containing every
element which is in exactly one of A and B. Also often
denoted A△B.

▶ A ∪ B = {x ∈ U | x ∈ A or x ∈ B}
▶ A ∩ B = {x ∈ U | x ∈ A and x ∈ B}.
▶ $A^\complement$ = {x ∈ U | x /∈ A}
▶ A − B = {x ∈ U | x ∈ A and x /∈ B}.
▶ A ⊕ B = (A − B) ∪ (B − A).


>>key properties

![[Pasted image 20230904225027.png]]

-------
![[Pasted image 20230904225321.png]]

![[Pasted image 20230904225335.png]]
![[Pasted image 20230904225346.png]]
> Venn Diagram 



## Cartesian Products 

#products #Ordered_Paire 


>>Definition: ==Given two sets A and B, the Cartesian product of A and B, denoted as A × B, is defined as the set of all ordered pairs where the first element of each pair comes from set A, and the second element comes from set B.==

<mark style="background: #FFF3A3A6;">NOTE</mark>: An ordered pair is a different kind of thing from a set. It is a
collection of two things (possibly equal) which come with an order
(there is a first thing and a second thing)

Here are four different ordered pairs:
(1, 2), (2, 1), (2, 2), (1, 1)
Ordered pairs are used for coordinate geometry in 2-dimensions,
but also for many other things in Computer Science. The two
things need not be numbers. For example ({1, 2, 3}, { }) is an
ordered pair the two components of which are sets.
For sets A and B we define
A × B = {(a, b) | a ∈ A and b ∈ B}


<mark style="background: #FFF3A3A6;">NOTE</mark>:The Cartesian product of an empty set and a set containing only one element is an empty set. 
                                            So: {} × {1} = {} 
In this case, there are no ordered pairs because the empty set does not contain any elements to form pairs with the elements of the set {1}. Therefore, the result is an empty set, denoted as {}.

Mathematically:

$A \times B$  and $B \times A$ are not the same 

$A = \{ 1\}$
$A = \{ 2\}$


$A\times B$ = $\{ (1, 2)\}$
$B\times A$ = $\{ (2, 1)\}$

>Tuple 
>Note that A × B and B × A are different in general.
Also note that (A × B) × C is not the same as A × (B × C).
As well as ordered pairs, we can have ordered triples, and more
generally n-tuples for any n ∈ N
>

 * *$()$ a 0-tuple
 * $(2)$ a 1-tuple
 * (7, 8) are 2-tuple

The set of all n-tuples built from elements of A is written
A × · · · × A with n copies of A. This is often written $A^n$.
More generally, if we have n sets A1,A2, · · · ,An we define

i=1
Ai = {(a1, a2, · · · , an) | a1 ∈ A1 and a2 ∈ A2 and · · · and an ∈ An}
 $\prod_{i=1}^{n} A_{i} =\{a_{1}, a_{2}, a_{3}, \dots| a_{1} \in A_{1}\  AND \ a_{2} \in A_{2} \dots AND \ a_{n} \in A_{n}\}$

------
### Relations 
#Relations
FOR DETAILS: CHECK TEXTBOOK P.573

>Binary relationship 
Def:
▶ a pair of sets, A and B,
(This means: let’s call them A and B for now because we
need to mention them in the next part),
together with
▶ a subset of A × B

In mathematics, a binary relation is a special structure that describes the relationship between elements of two or more sets. A binary relation associates elements of one set, called the domain, with elements of another set, called the codomain. A binary relation can be written as a set of ordered pairs, such as (x, y). For example, if A and B are sets, then <mark style="background: #ABF7F7A6;">a binary relation R from A to B is a subset of the Cartesian product of A and B (A x B).</mark>If the pair (a,b) belongs to the set R, one often writes aRb to denote their relation. The statement ($x$,$y$)∈$R$ reads "_x_ is _R_-related to _y_" and is denoted by _xRy_.The domain of definition or active domain of R is the set of all x such that xRy for at least one y. The codomain of definition, active codomain, image or range of R is the set of all y such that xRy for at least one x. The field of R is the union of its domain of definition and its codomain of definition



$A = \{ 1, 2, 3\}$
Binary relation on A 
subset of $A \times A$ 
e.g., $\{ (1, 2) ,( 2, 2 ) , (2, 3)\} \subset A \times B$

===

There are 16 binary ralation on thee set $\{1,2\}$
		 * The cartesian product of it is $\{ \{1, 1\},\ \{1, 2\} ,\{2, 1\}, \{2, 2\} \}$
		 * The sixteen possible binary relation
1. {}
2. {(1, 1)}
3. {(1, 2)}
4. {(2, 1)}
5. {(2, 2)}
6. {(1, 1), (1, 2)}
7. {(1, 1), (2, 1)}
8. {(1, 1), (2, 2)}
9. {(1, 2), (2, 1)}
10. {(1, 2), (2, 2)}
11. {(2, 1), (2, 2)}
12. {(1, 1), (1, 2), (2, 1)}
13. {(1, 1), (1, 2), (2, 2)}
14. {(1, 1), (2, 1), (2, 2)}
15. {(1, 2), (2, 1), (2, 2)}
16. {(1, 1), (1, 2), (2, 1), (2, 2)}


* Diagram of binary relation are very important 
* 



Comparison Between sets, pairs and bags

|orders |repeat |
|:--:|:--:|:---|
|set|0|0|
|list|1|1|
|bags|0|1|

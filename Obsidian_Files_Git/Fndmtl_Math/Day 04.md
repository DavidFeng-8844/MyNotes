#Predicate_Logic 
  
Propositional logic and predicate logic are both formal systems in mathematical logic, but they differ in their scope and expressive power.

1. **Propositional Logic:**
    
    - Deals with propositions or statements that are either true or false.
    - Propositions are usually represented by variables (p, q, r, etc.), and logical connectives (such as AND, OR, NOT) are used to combine these propositions to form more complex statements.
    - It doesn't deal with the internal structure of propositions or the relationships between elements within them.

2. **Predicate Logic (First-Order Logic):**
    
    - Allows for the representation of relationships between objects, properties of objects, and quantification over objects.
    - Uses variables, predicates, and quantifiers to express more intricate relationships and statements about objects in a domain.
    - Quantifiers, such as ∀ (for all) and ∃ (there exists), are used to express generality or existence over a domain of discourse.
    

In summary, propositional logic deals with simple true/false propositions and their combinations, while predicate logic allows for more complex expressions involving variables, predicates, and quantifiers to represent relationships and properties within a specified domain. Predicate logic is more expressive and is commonly used for formalizing statements in mathematics, computer science, and philosophy.

The predicate logic talks about <mark style="background: #ABF7F7A6;">individual thing</mark>s 

The set of all things is called the Domain or the Universe of Discourse 

>Visualisation
![[Pasted image 20230907095543.png]]

The Domain D can be seen as a set of separate of (discrete) dots.

A one-argument (or unary) predicate P picks out a subset of D. Those X $\in$ D for which P(x) holds.


A two-argument (or binary) predicate R picks out a subset of D ⇥ D. Those (x, y) for which R(x, y) holds. You can show these pairs by drawing arrows.


>Predicates more than one argument 

Let
I R(m, n) stand for m $\leq$  n, and
I S(m1,m2,m3) stand for m1 = m2 + m3.
I R(2, 2) is true; R(4, 0) is false
I S(3, 2, 1) is true; S(1, 2, 3) is false

## ==Quantifiers

> ==Universal ==Quantifiers

$\forall$ n, n $\leq$ n
means for all values of n in the domain, n $\leq$ n.

==Existenstiel== 

$\exists$n n $\leq$ n
means for some value of n in the domain, n $\leq$ 2.

Features:

Highest Precedence of all 


Nested ones 

Example
1. $\exists$n $\forall$ m m$\leq$ n. Domain is Z.
 $\exists$n( $\forall$ m m$\leq$ n).
It means can we find a n $\forall$  m $\leq$ n ( Is there a biggest integer?) 
1. $\exists$ m $\forall$ n m $\leq$  n. Domain is Z. (Is there a smallest integer )
2. $\exists$ m $\forall$ n m $\leq$  n. Domain is N. A smallest Number '0' exists  so it's true
3. $\forall$ n $\exists$ m m $\leq$  n Domain is Z

Predicates can only take individual can't take like this $P(P()$)

## Logical equivalences for negation 

$\neg \forall x P \equiv \exists x \neg P$ 
$\neg \exists x P \equiv \forall x\neg P$
## Interaction of quantifiers with $\land$ and $\lor$ 


## quantifiers with restricted domains 


e.g., 
$\exists \in A\ S(a)$


Say exactly one 


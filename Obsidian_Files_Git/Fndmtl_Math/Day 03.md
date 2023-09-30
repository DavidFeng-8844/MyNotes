
Tautology, Satisfiability, Logical Equivalence,
English statements into Propositional Logic


## Some Terminology 

>Tautology
A logical formula that has the value true whatever the values of its
component propositions is called a tautology. For example p ∨ ¬p
is a tautology.

>Contradiction
A statement that has value false whatever the values of its
component propositions is called a contradiction. For example
p ∧ ¬p is a contradiction.

>Contingency
A logical formula that is neither a tautology nor a contradiction is
a contingency. For example p → q is a contingency.( which can either be true or false )

>Satisfiable & Unsatisfiable 
A logical formula that is not a contradiction is said to be
satisfiable. This means that there is some way of choosing truth
values for the variables that makes the formula true. Another way
of saying that a formula always takes the value false is to say that
it is unsatisfiable.


>Logical Equivalence

Let α and β be formulas (statements) in propositional logic. We
say α and β are equivalent if α ↔ β is a tautology. When this
happens we write α ≡ β. If they are not equivalent we write
α ̸≡ β.
▶ α $\equiv$ β <mark style="background: #ABF7F7A6;">is not a propositional logic formula. It’s a statement
about two formulas.</mark>
▶ α $\not\equiv$ β is not a propositional logic formula. It’s a statement
about two formulas.
▶ α ↔ β is a propositional logic formula.
▶ α ̸↔ β is not a statement of any kind and is nonsense in this
module 

EX1:
p → ¬q ≡ q → ¬p



>Turnstile symbols(Logically implies )
We say α logically implies β if α → β is a tautology. When this
happens we write α ⊨ β. When it does not happen we write α ⊭ β.





## Equivalence
![[Pasted image 20230906113453.png]]
![[Pasted image 20230906113730.png]]
Some key ones:
¬(p ∧ q) ≡ ¬p ∨ ¬q De Morgan’s law:
negated conjunction
¬(p ∨ q) ≡ ¬p ∧ ¬q De Morgan’s law:
negated disjunction

==Important==

==p → q ≡ ¬p ∨ q== simple to prove by truth table

## <mark style="background: #FFB86CA6;">Substitution</mark>

p ∨ q ≡ q ∨ p

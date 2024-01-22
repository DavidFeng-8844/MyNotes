# The 2018 Fund_Math answer sheet 
---
(a) Given the following propositions, translate the following natural language sentences into
propositional logic formulas.
a := "it is raining"
b := "the weather is good"
c := "I attend the exam"

(i). If it is not raining and the weather is good then I attend the exam.  
> $\neg a \land b  \rightarrow c $
> 
(ii) It is raining or the weather is good.

> $a \lor b $
> 
(iii) I attend the exam if and only if it is not raining.
> $c \leftrightarrow \neg a$  (use biconditional operator )

(b) Given the following propositions, translate the following propositional formulas into nat-ural language sentences.
p := "I eat cake"
q := "I drink tea"
r := "I drink coffee"
(i) $\neg (q \lor r)$
> I don't drink coffe or tea  

(ii) ($r \land q$)
> I dink tea and coffee

(iii) $p \rightarrow ((q  \lor r) \land \neg(q \land r))$
> I eat cake then I dirnk tea or coffee and don't drink tea and coffee both.

(c.) Construct a truth table for the following propositional formula.
(i.) $(p \land p) \rightarrow (\neg \lor r)$

|p|q|r|Proposition|
|:---:|:--:|:--:|:---:|
|1|0|0|1|
|1|0|1|1|
|1|1|0|0|
|1|1|1|1|
|0|0|0|1|
|0|0|1|1|
|0|1|0|1|
|0|1|1|1|

(ii) Is the formula in part (c )(i) a contingency, a tautology or a contradiction? Justify
your answer

> It is a contingency which, since it can be true or false depends on the input.

(d) Translate each of the following natural language sentences into predicate logic. In each case state what domain you are using.
(i) All students study Fundamental Mathematical Concepts.
> $\forall _S M$

(ii) Some module is studied by all students.
> $\forall_s Math(s) $ The domain is all students  


(ii) Some module is studied by all students.
> $\exist_m (Student(m))$ The discourse is all modules

(e) Translate each of the predicate logic formula into natural language.
(i) $\neg \exist xP(x)$ where the domain consists of all people and P(x) := x is invincible.

> There does not exist a person such that the person is invincible.

(ii) $\exist x\forall y P(x, y)$ where the domain consists of all people and P(x, y) := x is friends with y.

> There exist a person is with friends with all people.

(g.) Show that $\neg((\neg a \land \neg b) \lor (\neg a \land b)) \equiv a$

> $\neg((\neg a \land \neg b) \lor (\neg a \land b))$ 
> $\equiv(a \land b) \lor (a \land \neg b)$> (Accoring to distributive law)
> $\equiv a \land (b \lor  \neg b)$
> $\equiv a \lor true$ (according to the domination law for $\lor$)
> $\equiv   a$

## Question 2
(a) Let U = \{0, 1, 2, 3, 4, 5, 6, 7\}, A = \{1, 2, 3\} and B = \{2, 6\}. Compute
(i) $A\cup B$ = \{1, 2, 3, 6}
(ii) $A \cap U = \{1, 2 , 3\}$
(iii) U \\ B = \{0, 1, 3, 4, 5, 7\}
(iv) $A \cap B = \{2\}$
(v) $A \cup \empty = A$
(vi) $\mathcal{P}(B) = \{\{2\}, \{6\}, \{2, 6\}, \{\}\} $
(vii) $\{2n | n \in A\} = \{2, 4, 6\}$
(b)See on ipad
(.c) The set of integers that are a multipe of 6 can be denoted by $\{6n | n \in N\}$ since 6n = 2n $\times$ 3 every element of this set belongs to the set of numbers.
(d) Prove using Induction that $|\mathcal(P)(A)| = 2^n$ for every set A of size $n \in N$
Base case: n = 0, A is an empty set and $2^n = 1$ which is the RHS.  The powerset of A includes empty set itself, so the cardinality of it is 1 which is the LHS which prove the equation.
The Iniductive steps: For any sets U, V, where $|\mathcal{P}(U)| = 2^n , |\mathcal{P}(V)| = 2^{n+1} $

## Question 3
(a) Let $f: A \rightarrow B $ Be a Function. Define what it means for $f$ to be 
(i) Injective
If f is a function from A to B, then we say f is injective or
one-to-one if it has the property that different things in A always
get sent to different things in B.

(ii) Surjective
The image of a function is a subset of the codomain, if this subset is all of the codomain we say the function is surjective or that the function is onto.

Bijective
A function which is both injective and surjective is said to be
bijective, or to be a one-to-one correspondence.
(iii)R = \{(0, 0), (1,1), (2, 1), (3,4), (4,3)\} over set {0, 1, 2, 3, 4}
|Property|Yes/No|
|:---:|:---:|
|Injective|No|
|Surjective|No|
|Bijective|No|
(b) Let f(x) :=
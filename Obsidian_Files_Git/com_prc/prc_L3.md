# Minimisation 

Def: optimising some criterias

1. No of transistors 
2. No of types of gates 
3. Depth of Logic gates 
4. Fan-in/out (refer to the number of inputs and outputs, respectively, that a particular gate or circuit can accommodate or drive.)

	Why: 
	- There is a limit to transistor density 
	- cost implication 
	- propogation time (depth)
	- bug finding and not easy to go wrong 

# Karnaugh maps
![[Pasted image 20240228150124.png]]
## Definition 

>Karnaugh Map
>
It is transformed from truth table to a two-dimensional grid, which is ordered in gray code, and each cell position represents one combination of inpout condition, And each cell represent the corresponding output value of the boolean function.(is an ordering of the [binary numeral system](https://en.wikipedia.org/wiki/Binary_numeral_system "Binary numeral system") such that two successive values differ in only one [bit](https://en.wikipedia.org/wiki/Bit "Bit") (binary digit).)

We should find minterm(minimal terms) rectangle (an area that is a power of two (i.e., 1, 2, 4, 8...)) as large as possible without any containing 0s, and the grouping might overlap each other
![[Pasted image 20240228211450.png]]

Once the Karnaugh has been constructed. 
For the red grouping 
- A is the same and is equal to 1 throughout the box, therefore it should be included in the algebraic representation of the red minterm
- B doesn't maintain the same state, and should therefor be excluded 
- C does not change, $\bar{C}$ should be included 
- D changes 
Therefore, the first minterm in the Boolean sum-of-product is $A\bar{C}$  

For the green grouping A and B maintain the same state, therefore it is $A\bar{B}$, For the purple grouping, BCD doesn't change, so it is the $BC\bar{D}$ 

## Inverses 
The three terms to cover the inverse are all shown with grey boxes with different colored borders:

- brown: $\bar{AB}$ 
- gold: $\bar{AC}$
- blue: BCD
![[Pasted image 20240228214102.png]]
## Don't Care 
Karnaugh maps also allow easier minimizations of functions whose truth tables include "[don't care](https://en.wikipedia.org/wiki/Don%27t-care_(logic) "Don't-care (logic)")" conditions. A "don't care" condition is a combination of inputs for which the designer doesn't care what the output is. Therefore, "don't care" conditions ==can either be included in or excluded from any rectangular group, whichever makes it larger.== ==They are usually indicated on the map with a dash or X.==
## References 

[Wikipedia](https://en.wikipedia.org/wiki/Karnaugh_map)

r
# Building gates from Nands 

We can build a NOT gate from NAND gate
and build a AND gate from NAND gate since $\neg \neg(a \land b) = a \land b$ 
![[Pasted image 20240227114547.png]]
> Or Gate 

Since $$x \lor y = \neg\neg x \lor \neg x\neg y = \neg(\neg x \land \neg y)$$
![[Pasted image 20240227114944.png]]

# Multiplexer 
A 2-to-a multiplexer has a boolean equation where A and B are the two inputs, $S_0$ is the selector input and Z is the output 

$$Z = (A \land \neg S_0) \lor (B \land S_0))$$

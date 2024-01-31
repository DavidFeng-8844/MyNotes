![[Pasted image 20240131214318.png]]
## Three Greek letters: Omega Theta Omicron

$\Omega$ for the best case $\Theta$ for the average and $\omicron$ for the worse case the Big O   

>for example: 
```python 
"""printing numbers"""
def print_nums(n):
	for i in n:
		print(i)
	for i in n: 
		print(i+1)
```
Although it might look like O(2N) But we normally ignore the constant 
![[Pasted image 20240131220430.png]]
In this case however it is 
>$O(N^2)$


AND in the cas e O(N^2 + N) that since N square us the dominant we can ignore the N 


> O(1) mean that regardless of the parameter n, the operation times would remains constant 
> ![[Pasted image 20240131222234.png]]

>O(logN)

For example in Binary search, to find [1 2 3 4 5 6 7 8] the worse case is 1 or 8, to find it, we need 3 operations so it is log2(8) = 3

AND there are the 
![[Pasted image 20240201000126.png]]
## List method

.append()
.pop() or .pop(index)
.insert(index, num)

.append() and pop() to the right is O(1) since no need to change the index of other elements

pop(index) to the left and insert() is O(N)
![[Pasted image 20240201001222.png]]
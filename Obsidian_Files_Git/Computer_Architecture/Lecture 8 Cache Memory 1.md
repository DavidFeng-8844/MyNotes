
# Storage 

>Locality : 
>Temporal
>Spatial 
>


# Machine Words Size 
The " Word size " refers to the number of bits
processed by a computer's CPU in one go


## memory Blocks and Cache lines 

![[L8-1.png]]

>==Block==
	The unit of data transfer. We break main memory into blocks. Each block holds m bytes (typically, 64 bits ) 
==Line==
	The cache is broken into multiple lines, each cache line holds exactly a memory block.


>Load and Store Sequence in Direct Mapped cache:

Read
>![[L8-2.png]] 
>1. check the index
>2. check the Tag
>3. check the Valid bit
>4.  Load the data 



Load 
![[L8-4.png]]

## Spatial Locality 

To fully make use of it, the CPU access nearby memory from the destination 

==Make the cache line larger than one byte==

![[L8-5.png]]

#### For Example:  
if a program reads from byte address 4 we’ll load alloW memory block 2 (both addresses 4 and 5) into cache line 2 spatial locality
# Type of Cache Miss

1. Compulsory Cache miss ==( Fist time )==
2. Conflict miss ==(One line hold multiple blocks)==


## Disadvantage of direct hit 

If memory address 2 and 6 map into the same cache line, what if a program repeatedly access to them.

---
## Locating Data in a Cache 

![[Pasted image 20231127225951.png]]

---
![[Pasted image 20231129114955.png]]
# Fully associative mapping 

-- A memory block can be load into any line of cache 

>==CONS==
>	1. Since there is no index field, the entire block address must be used as tag 



## Set Associative Mapping
Combine the benefits of direct and fully associative mappings
• Divide the cache lines into groups, called sets 

Some possible ones:![[L8-7.png]]
## Replacement Algorithm

>possible ones:

1.  Random Choice 
2.  First in first out (FIFO)
3. Least Recently Used (LRU)
4. Least Frequently Used (LFU)

---
## Write Policy for Cache Memory 

### Reference

[Cache Design - An Overview - YouTube](https://www.youtube.com/watch?v=1tvW8kzOpSA)

>Cache ==hit ==and ==cache miss== 

#### Example:
In the following examples, we assume a direct mapped cache
Assume the address to write to is already loaded in the cache

Write Hits

The data is presented in the cache 

Two Option:

>1. ==Write-through cache :

Update both the cache and main memory for each write

>2. ==Write-back cache:  

* Delay the update until cache block needs to be replaced 
* Need a dirty bit in the cache to mark the inconsistency
* Subsequent reads to the same memory address will be served by the
cache
![[Pasted image 20231129165320.png]]

![[L9-1.png]]

---

>==Write Miss 
> (What if the memory address you want to write is not in the cache)

Load it or not? 

### locate on write 

 >This strategy loads the newly written data into the cache



### Write around (Write no allocate)

>	The write operation goes directly to main memory without affecting the cache

## Some Terms 

- **Store (Write):** When a program writes data to memory, the data may be stored in both the cache and the main memory.
    
- **Load (Read):** When a program reads data from memory, the processor checks whether the data is already present in the cache. If it is, this is called a "cache hit," and the data is loaded from the cache. If the data is not in the cache, it's a "cache miss," and the data is loaded from the slower main memory into the cache for future use.

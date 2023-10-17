
# Storage 

>Locality : 
>Temporal
>Spatial 
>


# Machine Words 


## memory Blocks and Cache lines 

![[L8-1.png]]

>==Block==
	The unit of data transfer. We break main memory into blocks. Each block holds m bytes (typically, 64
==Line==
	The cache is broken into multiple lines, each cache line holds exactly a memory block .


>Load and Store Sequence in Direct Mapped cache:

Read
>![[L8-2.png]] 
>1. check the index
>2. check the Tag
>3. check the Valid bit
>4.  Load the data 

Load 
![[Pasted image 20231017101433.png]]

## Spatial Locality 

To fully make use of it, the CPU access nearby memory from the destination 

==Make the cache line larger than one byte==

![[Pasted image 20231017101647.png]]

#### For Example:  
if a program reads from byte address 4 we’ll load allof memory block 2 (both addresses 4 and 5) into cache line 2 spatial locality
# Type of Cache Miss

1. Compulsory Cache miss ==( Fist time )==
2. Conflict miss ==(One line hold multiple blocks)==
3. 
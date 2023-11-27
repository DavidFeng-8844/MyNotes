## Key Characteristic 

1. Faster access time require more cost per bit 
2. Greater capacity implies slower access time 

## location 

## Capacity 

## Performance

1. Access time 
2. Memory Cycle time 
3. Transfer rate 

---
## Access Method
1. ==Sequential Access== Start at the beginning of the memory and accesses records in order
	1. ==Direct access== move to a general region of memory (still depends on previous location)
2. ==Random Access== Directly address and access the selected memory address 

---
## Physical Type 
1. Semiconductor storage like RAM USB 
2. Magnetic Storage 
3. optical storage 

---
---
## Semiconductor Memory 

### RAM

1. Dynamic RAM (DRAM)
>Smaller, denser and less expensive 
1. Static RAM (SRAM)
less circuit and faster 

### ROM (Read only Memory )
> Permanent storage which cannot be changed 


## Error Detection and Correction 

1. Soft errors 
2. Hard Failures


## Parity bits 


### Redundancy for error checking


## Hamming Distance 

Between 2 strings of bits:

the number of bit positions in which 2 strings differ

### Minimum Hamming Distance 

Minimum Hamming Distance of a code

If distance is d , then d single bit errors are required to convert
any one valid code (string) into another code with the same


#### checksum

![[Pasted image 20231112124342.png]]
#Hamming_Distance
## Reference
1. 
![[Pasted image 20231115174033.png]]
[(7,4) Hamming Code (asecuritysite.com)](https://asecuritysite.com/calculators/hamming)

2. Error-Correcting Codes
	Andrew S, Computer Architecture, 2.2.4 Error-Correcting Codes (P78)
![[Pasted image 20231115230621.png]]

## Addressable Unit

To determine the number of address bits needed for a given memory size, you can use the formula:

Number of Address Bits=log⁡2(Memory Size)Number of Address Bits=log2​(Memory Size)

In your case, the memory size is 16 MB×32 bits16 MB×32 bits. First, let's convert the memory size to bits:

Memory Size in bits=16 MB×220 bytes/MB×32 bits/byteMemory Size in bits=16 MB×220 bytes/MB×32 bits/byte

Now, you can calculate the number of address bits:

Number of Address Bits=log⁡2(Memory Size in bits)Number of Address Bits=log2​(Memory Size in bits)

For the byte-addressable memory, each address refers to a single byte. In that case, the number of memory units that can be addressed is the same as the total number of bytes in the memory. You can calculate this using the formula:

Number of Memory Units=Memory SizeSize of each memory unitNumber of Memory Units=Size of each memory unitMemory Size​

Let's perform the calculations:

1. Memory Size in bits: Memory Size in bits=16 MB×220 bytes/MB×32 bits/byteMemory Size in bits=16 MB×220 bytes/MB×32 bits/byte Memory Size in bits=16×220×32 bitsMemory Size in bits=16×220×32 bits
    
2. Number of Address Bits: Number of Address Bits=log⁡2(Memory Size in bits)Number of Address Bits=log2​(Memory Size in bits)
    
3. For byte-addressable memory, Number of Memory Units: Number of Memory Units=Memory SizeSize of each memory unitNumber of Memory Units=Size of each memory unitMemory Size​ In this case, the size of each memory unit is 1 byte.
    

Let's calculate these values:

Number of Address Bits=log⁡2(16×220×32)Number of Address Bits=log2​(16×220×32)

Number of Memory Units (byte-addressable)=16×220×321Number of Memory Units (byte-addressable)=116×220×32​

Performing the calculations will give you the required results.



Let's calculate the results:

1. **Memory Size in bits:** Memory Size in bits=16×220×32 bitsMemory Size in bits=16×220×32 bits Memory Size in bits=224×32 bits=229 bitsMemory Size in bits=224×32 bits=229 bits
    
2. **Number of Address Bits:** Number of Address Bits=log⁡2(229)=29 bitsNumber of Address Bits=log2​(229)=29 bits
    
3. **Number of Memory Units (byte-addressable):** Number of Memory Units=16×220×321=16×220×32Number of Memory Units=116×220×32​=16×220×32
    

So, the results are as follows:

- **Number of Address Bits needed:** 29 bits
- **Number of Memory Units that can be addressed in a byte-addressable memory:** 16×220×3216×220×32

These values indicate that in a byte-addressable memory system with a total memory size of 16 MB * 32 bits, you would need 29 bits to address individual memory locations, and you can address 16×220×3216×220×32 memory units.

  
If it is a byte-addressable memory unit, the number of address bits needed remains the same. In this case, each address still refers to a single byte. The number of address bits is determined by the total size of the memory in bits, and it doesn't change based on whether the memory is byte-addressable or not.

So, whether the memory is byte-addressable or not, you still need 29 address bits to address the individual bytes in a 16 MB * 32-bit memory.
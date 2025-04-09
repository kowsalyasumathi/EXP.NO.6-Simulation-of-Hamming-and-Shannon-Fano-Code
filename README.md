# EXP.NO.6-Simulation-of-Hamming-and-Shannon-Fano-Code
6. Simulation of Hamming and Shannon-Fano Code

# AIM

To simulate Huffman and Shannon-Fano coding for a discrete memoryless source  and to determine the average codeword length, entropy, variance, redundancy, and its efficiency.

# SOFTWARE REQUIRED

Google Colab (python)

# ALGORITHMS

1. Huffman Coding Algorithm

     Input the probabilities of the source symbols.

     Construct a binary tree by merging the two lowest probability nodes iteratively.

     Assign binary codes to each symbol based on the tree structure.

     Compute the average codeword length, entropy, efficiency, and redundancy.

2. Shannon-Fano Coding Algorithm

     Input the message and compute the frequency of each symbol.

     Sort symbols in decreasing order of frequency.

     Recursively divide symbols into two groups with approximately equal probabilities.

     Assign binary codes (0 or 1) to each group and repeat the process.

     Generate the Shannon-Fano code for each symbol.

     Encode and decode the message using the generated codes.


# PROGRAM

#Huffman and Shannon-Fano coding
```
import numpy as np

import math 

L  = 0

hs = 0

p = []

lk = []

n = int(input("Enter the number of Samples : "))

for i in range (n): 

    pr = float(input(f"Enter the probability of sample values {i + 1}: "))  
    
    p.append(pr)
    
for j in range (n): 

    l = float(input(f"Enter the length of the sample values {j + 1}: ")) 
    
    lk.append(l)
 
for k in range (n):

    Avg1 = p[k] * lk[k]
    
    L = L + Avg1
    
for k in range (n):

    e = p[k] * math.log(1 / p[k], 2)
    
    hs = hs + e
    
hs = round(hs,3)

eff =  hs / L

eff = round(eff,3)

red =  round(1 - eff,3) 

var = 0

for k in range(n):

    var1 = p[k] * (lk[k]-L)**2
    
    var = var + var1
    
var = round(var,3)

print(f"Average Codeword Length is : {L}")

print(f"Entropy is : {hs}")

print(f"Efficiency is : {eff}")

print(f"Redudancy is : {red}")

print(f"Variance is : {var}")
```
# INPUT
```
Enter the number of Samples : 5
Enter the probability of sample values 1: 0.4
Enter the probability of sample values 2: 0.2
Enter the probability of sample values 3: 0.1
Enter the probability of sample values 4: 0.2
Enter the probability of sample values 5: 0.1
Enter the length of the sample values 1: 1
Enter the length of the sample values 2: 2
Enter the length of the sample values 3: 4
Enter the length of the sample values 4: 3
Enter the length of the sample values 5: 4
```
#OUTPUT

Average Codeword Length is : 2.2

Entropy is : 2.122

Efficiency is : 0.965

Redudancy is : 0.035

Variance is : 1.36

 
# RESULT / CONCLUSIONS

Thus the Shannon-Fano and Huffman coding were successfully simulated and the output is obtained.

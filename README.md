# Ex: 02 - Huffman - Shannon_fano
## AIM:
Consider a discrete memoryless source with symbols and statistics {0.125, 0.0625, 0.25, 0.0625, 0.125, 0.125, 0.25} for its output. Apply the Huffman and Shannon-Fano to this source. Show that draw the tree diagram, the average codeword length, Entropy, Variance, Redundancy, Efficiency.

## TOOLS REQUIRED:
Python IDE with Numpy and Scipy.

## PROGRAM:
```
# Huffman and Shannon-Fano coding

import numpy as np
import math

L = 0
hs = 0
p = []
lk = []

n = int(input("Enter the number of Samples : "))

for i in range(n):
    pr = float(input(f"Enter the probability of sample values {i + 1}: "))
    p.append(pr)

for j in range(n):
    l = float(input(f"Enter the length of the sample values {j + 1}: "))
    lk.append(l)

# Avg length of the code word
for k in range(n):
    Avg1 = p[k] * lk[k]
    L = L + Avg1

# Entropy
for k in range(n):
    e = p[k] * math.log(1 / p[k], 2)
    hs = hs + e

hs = round(hs, 3)

# Efficiency
eff = hs / L
eff = round(eff, 3)

# Redundancy
red = round(1 - eff, 3)

# Variance
var = 0

for k in range(n):
    var1 = p[k] * ((lk[k] - L) ** 2)
    var = var + var1

var = round(var, 3)

print(f"Average Codeword Length is : {L}")
print(f"Entropy is : {hs}")
print(f"Efficiency is : {eff}")
print(f"Redundancy is : {red}")
print(f"Variance is : {var}")
```
## CALCULATION:
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/da89b4c5-cb19-4c5a-bc6a-5f664529f048" />
<img width="720" height="1280" alt="image" src="https://github.com/user-attachments/assets/52ef77c2-7907-4e52-b61a-dbbdc39c9a1c" />



## OUTPUT:

<img width="701" height="287" alt="image" src="https://github.com/user-attachments/assets/50c93bb8-c794-4083-a57f-61432d328139" />


## RESULT:
The Huffman and Shannon-Fano of the given statistics {} using python are verified.

# Tom Philip - About Me and Portfolio
## About Me

Hi! I'm Tom.

I'm just your standard math nerd that's looking to find a career in pure maths or cryptography. You can find some of my CTF writeups below, as well as tutorials for the AP Computer Science exams!

# Writeups
## Tau As a Service (taas) - AngstromCTF
Here's the code for the following challenge, which is hosted on an external server.

```python
from blspy import PrivateKey as Scalar

# order of curve
n = 0x73EDA753299D7D483339D80809A1D80553BDA402FFFE5BFEFFFFFFFF00000001

with open('flag.txt', 'rb') as f:
	tau = int.from_bytes(f.read().strip(), 'big')
	assert tau < n

while True:
	d = int(input('gimme the power: '))
	assert 0 < d < n
	B = Scalar.from_bytes(pow(tau, d, n).to_bytes(32, 'big')).get_g1()
	print(B)
  ```
  
  The above code executes an implementation of the BLS cryptosystem, which is a digital signature scheme used by Ethereum and other cryptocurrencies. The `get_g1()` method seen takes the private key and right multiplies it by the G1 group generator. Which is an elliptic curve defined by BLS12-381.
  
  Next we notice that the challenge raises the flag to the power of any number, which is used as the private key for the BLS cryptosystem. We also find that the multiplicative order of n is extremely smooth (n-1 factors into several small factors). As such we can just consider the BLS as a hash function, as it is one way and inneficient to revert.
  
  Consider what we could do given $tau^a$ and $tau^b$, since the goal is to recover tau, we want to find the smallest possible value we can get by multiplying and dividing these values.
  
  For example, given $x^{12}$ and $x^8$, we can find $x^4$ by dividing $x^{12}$ by $x^8$. 
  
  Recall that raising tau to the power of a factor n-1, p sends tau to a smaller subgroup of size $\frac{n-1}{p}$. We can brute force all the elements in this group to recover several powers of tau, and use the above method to reduce it to tau.
  
  What follows is the pseudocode for the solve:
  
  ```
  for each prime divisor k of n-1:
  query server for d = (n-1)/k
  Compute from i = 0 ... n-1:
    if i^(n-1)/k * G1 matches, break, and store for k: ((n-1)/k, (i^(n-1)/k)) then break
    this step is ok since there are k different elements, and it's really just luck
  Now, we combine together results.
  while the  list of factor-power pairs has more than 1 element:
    take the first two:
      compute the coefficients of bezouts identity c0, c1 for k0 and k1
      replace the two pairs with (gcd(k0, k1), (v0)^c0*(v1)^c1)
  you should be remaining with (1, flag) at the end if n-1 is square free
  
  Should n-1 not be square free, compute the nth roots of it, and compute the correct element in a similar manner.
  ```
  
  Here is the implementation of the merge function which does that, given the powers exponents of the powers:
  ```py
  
  def merge(a, b):
      k0, v0 = a
      k1, v1 = b
      c0 = inverse(k0, k1)
      g = gcd(k0, k1)
      c1 = (g-c0*k0)
      assert c1%k1 ==0
      c1 = c1//k1
      return(g, (pow(v0, c0, n)*pow(v1, v1, n))%n)
  ```
  
  The following method runs the brute force to reverse the G1 operation:
  ```py
  def findThing(s, e):
    i = 0
    while True:
        p = pow(i, e, n)
        p = Scalar.from_bytes((p).to_bytes(32, 'big')).get_g1()
        if str(p)==s:
            return p
        i+=1
        if not i%10000:
            print(i)
  ```
  
  The remaining of the implementation is left as an exercise to the reader.
  
  ## helt or melt - MidnightSun CTF
  
  ## AP tutorials
  
  [Objects](./tutorials/Objects.md) <br/>
  [Inheritance](./tutorials/Inheritance.md) <br/>
  [Arrays](./tutorials/Arrays.md) <br/>
  [ArrayLists](./tutorials/ArrayLists.md) <br/>
  [Recursion](./tutorials/Recursion.md) <br/>
  [Searching](./tutorials/Searching.md) <br/>
  [Sorting](./tutorials/Sorting.md)
  

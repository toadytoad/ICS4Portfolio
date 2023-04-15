## Solving A Simpler Problem
Suppose I asked you to find me the 14th fibonnaci number. Well you know that a fibonnaci number is equal to the sum of the two previous fibonnaci numbers. So, naturally, you would find the 13th and 12th number, and for each you will find its sum, until a case of something you know.
Let's implement this in code:

```java
int fib(int n){
  //base case
  if(n==1||n==2){
    return 1;
  }
  return fib(n-1)+fib(n-2);
}
```

Notice how the functions calls itself from within itself, this is the key idea of recursion. The function keeps calling itself until it reaches a base case, at which point it will climb back up the call stack to report the answer to you.

## Finding The GCD of two numbers
An improved form of the euclidean algorithm states that the GCD(a, b) = GCD(b, a%b), where % denotes the remainder of a after being divided by b. Let's use this to create a recursive function to solve the GCD of two numbers:
What is the base case and what is the recursive step?
The base case is the GCD of any number, x, and 0. In this case the greatest common divisor is x, as all numbers divide 0. The recursive step is given as above.

Fill in the rest of the code:

```java
int gcd(int a, int b){
  if(/* base case condition */){
    return /* base case return */;
  }
  return /* recursive step */;
}
```

Replace the comments with the correct code, and test the function to see if it reports the correct answer.

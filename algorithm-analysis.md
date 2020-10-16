#### Algorithms Analysis
* Count how many primitive operations are executed, and use this number t as a measure of the running time of the algorithm.
* A function f(n) that characterizes the number of primitive operations that are performed as a function of the input size n.
* primitive operations
  * Assigning a value to a variable
  * Performing an arithmetic operation (for example, adding two numbers) 
  * Comparing two numbers
  * Accessing a single element of an array by index
  * Calling a method
  * Returning from a method
 
#### Function in Analysis of algorithms
* The Constant Function
   * f(n) = c
   * For any value of n there will be same value of c
* Logarithm Function
  * f (n) = log2 n
  * The most common base for the logarithm function in computer science is 2 as
    computers store integers in binary.
  * Examples
    * [log3 27] = 3, because ((27/3)/3)/3 = 1;
    * [log4 64] = 3, because ((64/4)/4)/4 = 1;
    * [log2 12] = 4, because (((12/2)/2)/2)/2 = 0.75 ≤ 1
* Linear Function
  * f(n) = n
* N-Log-N Function
  * f(n) = nlogn
  * This function grows a little more rapidly than the linear function and a lot less rapidly than the quadratic function.
* Quadratic Function
  * f(n) = n^2
  * There are many algorithms that have nested loops, where the inner loop performs a linear number of operations and the outer loop is performed a linear number of times
* Cubic Function
  * f(n) = n^3
* Exponential Function
  * f(n) = b^n
##### Asymptotic Analysis







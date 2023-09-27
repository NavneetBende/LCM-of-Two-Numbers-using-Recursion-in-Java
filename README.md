# LCM-of-Two-Numbers-using-Recursion-in-Java

LCM of Two Numbers using Recursion in Java
Here, in this page we will discuss the program to find the LCM of Two numbers using Recursion in Java Programming Language. We are given with two integers and need to find the LCM of the given numbers.  The LCM of two integers num1 and num2 is the smallest positive integer that is perfectly divisible by both num1 and num2(without a remainder). 

Example :

Input : num1 = 3 num2 = 21
Output : LCM of 3 and 21 is 21.
LCM of Two Numbers using Recursion in C++
Relationship Between HCF and LCM
To find the LCM of the given two numbers using recursion. We first calculate the HCF of the numbers using recursion and then Calculate the LCM using the following relationship : LCM * HCF = num1 * num2
Different Methods Discussed in this page :
We have discussed the following methods using recursion to find the HCF of given two numbers and then can find the LCM using that HCF.

Method 1 :Recursive Euclidean Algorithm: Repeated Subtraction to calculate the HCF
Method 2: Modulo Recursive Euclidean Algorithm: Repeated Subtraction to calculate the HCF
 
Method 1 :
This method is based on  Euclidean Algorithm.

Create a variable say HCF to hold the value return by getHCF(int num1, num2).
Then calculate the LCM = (num1 *num2)/HCF
Euclidean Algorithm
HCF of two numbers doesn’t change if smaller number is subtracted from a bigger number
Code to find LCM of a Number using Recursion
Run
public
class Main {
    // Recursive method to return gcd of a and b
    static int gcd(int a, int b) {
        if (a == 0) return b;
        return gcd(b % a, a);
    }
    // method to return LCM of two numbers
    static int lcm(int a, int b) {
        return (a / gcd(a, b)) * b;
    }
    // Driver method
    public
    static void main(String[] args) {
        int a = 15, b = 20;
        System.out.println("LCM of " + a + " and " + b + " is " + lcm(a, b));
    }
}
LCM of 15 and 20 is 60
Method 2
This method uses recursion.

In Addition, we are using modulo operation to reduce the number of subtractions required and improve the time complexity

For this method, you need to know how to calculate HCF, check this post here

We use repeated Modulo Recursive subtraction (Euclidean Algorithm) to calculate the HCF.

Run
public
class Main {
    public
    static void main(String[] args) {
        int num1 = 144, num2 = 32;
        int hcf = getHCF(num1, num2);
        System.out.println("The HCF: " + hcf);
        // LCM formula
        int lcm = (num1 * num2) / hcf;
        System.out.println("The LCM: " + lcm);
    }
    // This method improves complexity of repeated substraction
    // By efficient use of modulo operator in euclidean algorithm
    static int getHCF(int a, int b) {
        return b == 0 ? a : getHCF(b, a % b);
    }
}
Output
The HCF: 16
The LCM: 288

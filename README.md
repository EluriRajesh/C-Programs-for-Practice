# C# Programs

## 1. Fibonacci Series

### Description
The Fibonacci series is a sequence of numbers in which each number is the sum of the two preceding ones, usually starting with 0 and 1.

### Program

```csharp
using System;

class FibonacciSeries
{
    static void Main()
    {
        Console.Write("Enter the number of terms for the Fibonacci series: ");
        if (int.TryParse(Console.ReadLine(), out int n) && n > 0)
        {
            PrintFibonacciSeries(n);
        }
        else
        {
            Console.WriteLine("Please enter a valid positive integer.");
        }
    }

    static void PrintFibonacciSeries(int n)
    {
        int firstNumber = 0, secondNumber = 1, nextNumber;

        Console.WriteLine("Fibonacci Series:");
        Console.Write("{0} {1}", firstNumber, secondNumber);

        for (int i = 2; i < n; i++)
        {
            nextNumber = firstNumber + secondNumber;
            Console.Write(" {0}", nextNumber);
            firstNumber = secondNumber;
            secondNumber = nextNumber;
        }

        Console.WriteLine();
    }
}
```

---

## 2. Checking for Prime Number

### Description
A prime number is a natural number greater than 1 that has no positive divisors other than 1 and itself.

### Program

```csharp
using System;

class PrimeNumberCheck
{
    static void Main()
    {
        Console.Write("Enter a number to check if it is prime: ");
        if (int.TryParse(Console.ReadLine(), out int number))
        {
            if (IsPrime(number))
            {
                Console.WriteLine("{0} is a prime number.", number);
            }
            else
            {
                Console.WriteLine("{0} is not a prime number.", number);
            }
        }
        else
        {
            Console.WriteLine("Please enter a valid integer.");
        }
    }

    static bool IsPrime(int number)
    {
        if (number <= 1)
        {
            return false;
        }

        for (int i = 2; i <= Math.Sqrt(number); i++)
        {
            if (number % i == 0)
            {
                return false;
            }
        }

        return true;
    }
}
```

---

## 3. String Palindrome

### Description
A string palindrome is a string that reads the same forward and backward.

### Program

```csharp
using System;

class StringPalindrome
{
    static void Main()
    {
        Console.Write("Enter a string to check if it is a palindrome: ");
        string input = Console.ReadLine();

        if (IsPalindrome(input))
        {
            Console.WriteLine("{0} is a palindrome.", input);
        }
        else
        {
            Console.WriteLine("{0} is not a palindrome.", input);
        }
    }

    static bool IsPalindrome(string input)
    {
        int length = input.Length;

        for (int i = 0; i < length / 2; i++)
        {
            if (input[i] != input[length - i - 1])
            {
                return false;
            }
        }

        return true;
    }
}
```

---

## 4. Integer Palindrome

### Description
An integer palindrome is a number that remains the same when its digits are reversed.

### Program

```csharp
using System;

class IntegerPalindrome
{
    static void Main()
    {
        Console.Write("Enter an integer to check if it is a palindrome: ");
        if (int.TryParse(Console.ReadLine(), out int number))
        {
            if (IsPalindrome(number))
            {
                Console.WriteLine("{0} is a palindrome.", number);
            }
            else
            {
                Console.WriteLine("{0} is not a palindrome.", number);
            }
        }
        else
        {
            Console.WriteLine("Please enter a valid integer.");
        }
    }

    static bool IsPalindrome(int number)
    {
        int originalNumber = number, reversedNumber = 0, remainder;

        while (number != 0)
        {
            remainder = number % 10;
            reversedNumber = reversedNumber * 10 + remainder;
            number /= 10;
        }

        return originalNumber == reversedNumber;
    }
}
```

---

## 5. Armstrong Number

### Description
An Armstrong number (or narcissistic number) is a number that is equal to the sum of its own digits raised to the power of the number of digits.

### Program

```csharp
using System;

class ArmstrongNumberCheck
{
    static void Main()
    {
        Console.Write("Enter an integer to check if it is an Armstrong number: ");
        if (int.TryParse(Console.ReadLine(), out int number))
        {
            if (IsArmstrong(number))
            {
                Console.WriteLine("{0} is an Armstrong number.", number);
            }
            else
            {
                Console.WriteLine("{0} is not an Armstrong number.", number);
            }
        }
        else
        {
            Console.WriteLine("Please enter a valid integer.");
        }
    }

    static bool IsArmstrong(int number)
    {
        int sum = 0, temp = number, digits = number.ToString().Length;

        while (temp != 0)
        {
            int remainder = temp % 10;
            sum += (int)Math.Pow(remainder, digits);
            temp /= 10;
        }

        return sum == number;
    }
}
```

---

## 6. Avoiding Deadlocks

### Description
A deadlock occurs when two or more threads are blocked forever, waiting for each other. Avoiding deadlocks involves careful resource allocation and using proper synchronization techniques.

### Program

```csharp
using System;
using System.Threading;

class AvoidDeadlock
{
    private static readonly object lock1 = new object();
    private static readonly object lock2 = new object();

    static void Main()
    {
        Thread t1 = new Thread(Method1);
        Thread t2 = new Thread(Method2);

        t1.Start();
        t2.Start();

        t1.Join();
        t2.Join();

        Console.WriteLine("Finished without deadlocks.");
    }

    static void Method1()
    {
        lock (lock1)
        {
            Console.WriteLine("Thread 1 acquired lock1");
            Thread.Sleep(100);

            lock (lock2)
            {
                Console.WriteLine("Thread 1 acquired lock2");
            }
        }
    }

    static void Method2()
    {
        lock (lock1)
        {
            Console.WriteLine("Thread 2 acquired lock1");
            Thread.Sleep(100);

            lock (lock2)
            {
                Console.WriteLine("Thread 2 acquired lock2");
            }
        }
    }
}
```

---

## 7. Factorial

### Description
The factorial of a non-negative integer \( n \) is the product of all positive integers less than or equal to \( n \). It is denoted as \( n! \).

### Program

```csharp
using System;

class Factorial
{
    static void Main()
    {
        Console.Write("Enter a number to calculate its factorial: ");
        if (int.TryParse(Console.ReadLine(), out int number) && number >= 0)
        {
            Console.WriteLine("Factorial of {0} is {1}", number, CalculateFactorial(number));
        }
        else
        {
            Console.WriteLine("Please enter a valid non-negative integer.");
        }
    }

    static long CalculateFactorial(int number)
    {
        if (number == 0 || number == 1)
        {
            return 1;
        }

        long factorial = 1;
        for (int i = 2; i <= number; i++)
        {
            factorial *= i;
        }

        return factorial;
    }
}
```

---

## 8. Reversing Strings

### Description
Reversing a string involves rearranging its characters in the opposite order.

### Program

```csharp
using System;

class ReverseString
{
    static void Main()
    {
        Console.Write("Enter a string to reverse: ");
        string input = Console.ReadLine();

        string reversed = Reverse(input);
        Console.WriteLine("Reversed string: {0}", reversed);
    }

    static string Reverse(string input)
    {
        char[] charArray = input.ToCharArray();
        Array.Reverse(charArray);
        return new string(charArray);
    }
}
```

---

## 9. Removing Repeated Elements from an Array

### Description
Removing repeated elements from an array involves creating a new array that contains only unique elements from the original array.

### Program

```csharp
using System;
using System.Collections.Generic;

class RemoveDuplicates
{
    static void Main()
    {
        int[] array = { 1, 2, 3, 1, 2, 4, 5, 6, 4 };
        int[] uniqueArray = RemoveDuplicatesFromArray(array);

        Console.WriteLine("Array with duplicates removed: {0}", string.Join(", ", uniqueArray));
    }

    static int[] RemoveDuplicatesFromArray(int[] array)
    {
        HashSet<int> uniqueElements = new HashSet<int>(array);
        return new int[uniqueElements.Count];
    }
}
```

---

## 10. Printing Patterns

### Description
Printing patterns involves creating various designs or shapes using characters like `*`, spaces, or numbers. Below is an example of printing a pyramid pattern.

### Program

```csharp
using System;

class PrintPatterns
{
    static void Main()
    {
        Console.Write("Enter the number of rows for the pyramid: ");
        if (int.TryParse(Console.ReadLine(), out int rows) && rows > 0)
        {
            PrintPyramid(rows);
        }
        else
        {
            Console.WriteLine("Please enter a valid positive integer.");
        }
    }

    static void PrintPyramid(int rows)
    {
        for (int i = 1; i <= rows; i++)
        {
            for (int j = rows; j > i; j--)
            {
                Console.Write(" ");
            }

            for (int k = 1; k <= (2 * i - 1); k++)
            {
                Console.Write("*");
            }

            Console.WriteLine();
        }
    }
}
```

---


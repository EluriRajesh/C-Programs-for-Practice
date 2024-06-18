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

Feel free to copy and paste these examples into your GitHub repository's README or any other markdown file to showcase your C# programs.

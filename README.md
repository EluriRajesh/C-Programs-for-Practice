# Programs

1). Fibbonacci series: The Fibonacci series is a sequence of numbers in which each number (after the first two) is the sum of the two preceding ones. The sequence typically starts with 0 and 1. Therefore, the first few terms in the Fibonacci series are:
0, 1, 1, 2, 3, 5, 8, 13, 21, 34, ...

```csharp
using System;

class FibonacciSeries
{
    static void Main()
    {
        int n, firstNumber = 0, secondNumber = 1, nextNumber;
        
        Console.Write("Enter the number of terms for the Fibonacci series: ");
        n = int.Parse(Console.ReadLine());
        
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

# Programs

1). Fibbonacci series: Program to display any given number of integers of the Fibonacci series. In the Fibonacci series, each number is equal to the sum of the two numbers that precede it.
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

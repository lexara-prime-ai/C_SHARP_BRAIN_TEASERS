### BRAIN TEASERS
This repository contains some snippets for jogging your memory

*Example* : Exception Handling(*Ignored Exceptions*)
```csharp
using System;

class Program
{
    static void Main()
    {
        int[] numbers = { 1, 2, 3 };

        try
        {
            int result = numbers[4] / 0;
            Console.WriteLine($"Result: {result}");
        }
        catch (Exception ex)
        {
            Console.WriteLine($"An error occurred: {ex.Message}");
        }
    }
}
```

OUTPUT :

```powershell
C:\> An error occurred: Index was outside the bounds of the array.
```
**NB**: When the runtime encounters an out-of-bounds array access, it's considered a more serious error, and the runtime immediately terminates the program without proceeding to the following lines of code. This is why you're not seeing the "Divide by zero" exception being thrown and caught in your try-catch block.

SOLUTION :

```csharp
using System;

class Program
{
    static void Main()
    {
        int[] numbers = { 1, 2, 3 };

        // HANDLE INDEX OUT OF BOUNDS EXCEPTION
        try
        {
            // IF WE TRY TO ACCESS AN INDEX THAT DOESN'T EXIST
            // OR IS 'OUTSIDE THE EXISTING RANGE'
            // AN EXCEPTION WILL BE THROWN | Index was outside the bounds of the array
            int result = numbers[2];
            Console.WriteLine($"Result: {result}");
        }
        catch (IndexOutOfRangeException ex)
        {
            Console.WriteLine($"An error occurred: {ex.Message}");
        }

        // HANDLE DIVIDE BY ZERO EXCEPTION
        try
        {
            // IF WE ATTEMPT TO DIVIDE BY ZERO(0)
            // ANOTHER EXCEPTION WILL BE THROWN | Attempted to divide by zero
            int result = numbers[2] / 0;
            Console.WriteLine($"Result: {result}");
        }
        catch (DivideByZeroException ex)
        {
            Console.WriteLine($"An error occurred: {ex.Message}");
        }
    }
}
```

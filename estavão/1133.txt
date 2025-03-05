namespace _1133
{
    using System;

    class Program
    {
        static void Main()
        {
            // Read the two integer numbers
            string[] input = Console.ReadLine().Split();

            // Check if we have exactly two inputs
            if (input.Length != 2)
            {
                Console.WriteLine("Please enter exactly two positive integers.");
                return; // Exit the program if input is invalid
            }

            int X, Y;

            // Try to parse the integers
            if (!int.TryParse(input[0], out X) || !int.TryParse(input[1], out Y) || X <= 0 || Y <= 0)
            {
                Console.WriteLine("Invalid input. Please enter two positive integers.");
                return; // Exit the program if parsing fails
            }

            // Determine the range
            int start = Math.Min(X, Y);
            int end = Math.Max(X, Y);

            // Create a list to store valid numbers
            var validNumbers = new List<int>();

            // Check each number in the range
            for (int i = start; i <= end; i++)
            {
                if (i % 5 == 2 || i % 5 == 3)
                {
                    validNumbers.Add(i);
                }
            }

            // Print the valid numbers in ascending order
            foreach (var number in validNumbers)
            {
                Console.WriteLine(number);
            }
        }
    }
}

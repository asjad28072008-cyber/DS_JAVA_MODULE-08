# Ex13 Fill the First 10 Elements of an Array with a Constant using Arrays.fill()
## DATE:
## AIM:
To write a Java program that fills the first 10 elements of an array with a constant value using the Arrays.fill() method.
## Algorithm
1. Start the program.Import the java.util.
2. Arrays and java.util.Scanner libraries.
3. Declare and instantiate an integer array of size 10.
4. Read the constant value from the user using a Scanner object.
5. Use Arrays.fill() to populate the first 10 elements with the user's input.
6. Print the updated array and close the scanner.

## Program:
```
/*
Program to FILL the first 10 elements of an array with a constant value using the Arrays.fill() method.
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```
import java.util.Arrays;
import java.util.Scanner;

public class FillArrayFromInput {
    public static void main(String[] args) {
        // Create an integer array with 10 elements
        int[] numbers = new int[10];
        
        // Setup Scanner for user input
        Scanner scanner = new Scanner(System.in);
        
        System.out.print("Enter the constant value to fill the array: ");
        int userInput = scanner.nextInt();
        
        // Fill all 10 elements with the user's input value
        Arrays.fill(numbers, 0, 10, userInput);
        
        // Print the final array
        System.out.println("\nArray after using Arrays.fill():");
        System.out.println(Arrays.toString(numbers));
        
        // Close the scanner resource
        scanner.close();
    }
}

```
## Output:

<img width="735" height="276" alt="image" src="https://github.com/user-attachments/assets/3fe69e5d-2a5a-49aa-978e-a39343dc944f" />


## Result:
The program successfully fills the first 10 elements of the array with the constant value 5 using the Arrays.fill() method.

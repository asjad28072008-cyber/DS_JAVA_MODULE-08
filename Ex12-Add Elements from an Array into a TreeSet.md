# Ex12 Add Elements from an Array into a TreeSet
## DATE:
## AIM:
To write a Java program that adds elements from an array into a TreeSet and displays the elements in sorted order.
## Algorithm
1. Start the program.
2. Initialize an array with a predefined set of elements.
3. Create an instance of TreeSet to store the elements automatically in sorted order.
4. Iterate through the array using a loop and add each element to the TreeSet using the add() method.
5. Display the sorted elements of the TreeSet and Stop the program.


## Program:
```
/*
Program that adds elements from an array into a TreeSet and displays the elements in sorted order.
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```
import java.util.Scanner;
import java.util.TreeSet;

public class TreeSetExample {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);

        // Step 1: Get the size of the array from the user
        System.out.print("Enter the number of elements: ");
        int size = scanner.nextInt();

        // Step 2: Initialize the array based on user input
        Integer[] numbersArray = new Integer[size];
        System.out.println("Enter " + size + " integers:");
        for (int i = 0; i < size; i++) {
            numbersArray[i] = scanner.nextInt();
        }

        // Step 3: Create a TreeSet
        TreeSet<Integer> sortedSet = new TreeSet<>();

        // Step 4: Add elements from the array into the TreeSet
        for (Integer num : numbersArray) {
            sortedSet.add(num);
        }

        // Step 5: Display the elements in sorted order
        System.out.println("\nElements in TreeSet (Sorted & Unique): " + sortedSet);
        
        scanner.close();
    }
}

```

## Output:

<img width="787" height="452" alt="image" src="https://github.com/user-attachments/assets/e9537328-cfd9-43a4-b8f4-44a02e352aaf" />


## Result:
The program successfully adds elements from an array into a TreeSet.

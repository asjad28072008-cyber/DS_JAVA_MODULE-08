# Ex15 Value Existence Check in a TreeMap
## DATE:
## AIM:
To write a Java program that checks whether a given value exists in a TreeMap.

## Algorithm
1.Start the program and initialize a Scanner object for reading console input.
2.Create an empty TreeMap instance to store the key-value pairs.
3.Prompt the user to enter the total number of entries they wish to add.
4.Loop through the specified count to read each integer key and string value, then insert them using put().
5.Prompt the user to input the specific target value they want to verify.
6.Check for the presence of the target value using the containsValue() method.
7.Print whether the value exists or not, then close the scanner and Stop

## Program:
```
/*
Program to checks whether a given value exists in a TreeMap.
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```
import java.util.Scanner;
import java.util.TreeMap;

public class DynamicTreeMapCheck {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        TreeMap<Integer, String> map = new TreeMap<>();

        // Step 1: Get the number of elements from the user
        System.out.print("Enter the number of entries to add to the TreeMap: ");
        int count = scanner.nextInt();

        // Step 2: Populate the TreeMap dynamically
        for (int i = 0; i < count; i++) {
            System.out.print("Enter key (integer) for entry " + (i + 1) + ": ");
            int key = scanner.nextInt();
            scanner.nextLine(); // Consume the leftover newline character

            System.out.print("Enter value (string) for entry " + (i + 1) + ": ");
            String value = scanner.nextLine();

            map.put(key, value);
        }

        // Step 3: Get the target value to search for
        System.out.print("\nEnter the value you want to search for: ");
        String valueToCheck = scanner.nextLine();

        // Step 4: Verify existence and display the result
        if (map.containsValue(valueToCheck)) {
            System.out.println("Result: Value '" + valueToCheck + "' exists in the TreeMap.");
        } else {
            System.out.println("Result: Value '" + valueToCheck + "' does not exist in the TreeMap.");
        }

        scanner.close();
    }
}

```

## Output:

<img width="727" height="487" alt="image" src="https://github.com/user-attachments/assets/36dda933-f34e-4e6d-9cc1-b5e361b60b95" />



<img width="732" height="462" alt="image" src="https://github.com/user-attachments/assets/c42a5ce4-c0d1-447a-9ebb-ed5527867c19" />


## Result:
Thus, the program successfully checks whether a specified value exists in a TreeMap using the containsValue() method.

# Ex11 Convert HashSet to ArrayList in Java
## DATE: 01.09.2026
## AIM:
To convert a collection of distinct integers stored in a HashSet into an ArrayList and display its contents.
## Algorithm
1. Start the program and import the required classes from java.util package (HashSet and ArrayList).
2. Create a HashSet object and populate it with a collection of distinct integers using the add() method.
3. Create an ArrayList object and pass the HashSet instance into the ArrayList constructor to copy all elements.
4. Display the contents of both the original HashSet and the newly created ArrayList to verify the conversion.
5. Stop the program execution.


## Program:
```
/*
Program to To convert a collection of distinct integers stored in a HashSet into an ArrayList and display its contents.
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```
import java.util.HashSet;
import java.util.ArrayList;
import java.util.Scanner;

public class HashSetToArrayListUser {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        HashSet<Integer> numbersSet = new HashSet<>();

        // Step 2: Accept user inputs to populate the HashSet
        System.out.print("Enter the number of elements to add: ");
        int count = scanner.nextInt();

        System.out.println("Enter " + count + " integers:");
        for (int i = 0; i < count; i++) {
            int num = scanner.nextInt();
            numbersSet.add(num);
        }
        
        System.out.println("\nOriginal HashSet: " + numbersSet);
        
        // Step 3: Convert HashSet to ArrayList using constructor passing
        ArrayList<Integer> numbersList = new ArrayList<>(numbersSet);
        
        // Step 4: Display the converted ArrayList
        System.out.println("Converted ArrayList: " + numbersList);
        
        scanner.close();
    }
}
```

## Output:


<img width="573" height="626" alt="image" src="https://github.com/user-attachments/assets/615f1641-7159-4ac5-9a02-626b0d96fcc8" />



## Result:
The program successfully converts a collection of distinct integers stored in a HashSet into an ArrayList






















# Ex12 Add Elements from an Array into a TreeSet
## DATE: 01.09.2026
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

<img width="705" height="516" alt="image" src="https://github.com/user-attachments/assets/7503a21d-100a-4b0d-b1f4-782e407eb41a" />



## Result:
The program successfully adds elements from an array into a TreeSet.





















# Ex13 Fill the First 10 Elements of an Array with a Constant using Arrays.fill()
## DATE: 01.09.2026
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

<img width="755" height="265" alt="image" src="https://github.com/user-attachments/assets/3c673a84-ab75-46b9-bacf-9294587043d2" />



## Result:
The program successfully fills the first 10 elements of the array with the constant value 5 using the Arrays.fill() method.




















# Ex14 Tracking the First Unique Number in a Stream using LinkedHashMap
## DATE: 01.09.2026
## AIM:
To implement a program that tracks the first unique (non-repeating) number in a stream of integers using a LinkedHashMap.

## Algorithm
1. Initialize a LinkedHashMap<Integer, Boolean> to maintain the insertion order of numbers along with a boolean flag indicating their uniqueness status (true for unique, false for duplicate).
2. Read numbers sequentially from the incoming stream of integers.
3. Update the map for each incoming number: if the number is not present in the map, insert it with a value of true. If it is already present, update its value to false.
4. Find the first unique number by iterating through the LinkedHashMap entry set in insertion order and returning the first key that has a value of true.
5. Return -1 (or an appropriate indicator) if the map is empty or if all numbers in the stream have been updated to false.
   

## Program:
```
/*
Program to tracks the first unique (non-repeating) number in a stream of integers using a LinkedHashMap.
Developed by: MUHAMMAD ASJAD E
RegisterNumber:  212225240091
*/
```

```
import java.util.LinkedHashMap;
import java.util.Map;
import java.util.Scanner;

public class FirstUniqueNumberTracker {
    
    private final LinkedHashMap<Integer, Boolean> numMap;

    public FirstUniqueNumberTracker() {
        this.numMap = new LinkedHashMap<>();
    }

    public void add(int number) {
        if (!numMap.containsKey(number)) {
            numMap.put(number, true);
        } else {
            numMap.put(number, false);
        }
    }

    public int getFirstUnique() {
        for (Map.Entry<Integer, Boolean> entry : numMap.entrySet()) {
            if (entry.getValue()) {
                return entry.getKey();
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        FirstUniqueNumberTracker tracker = new FirstUniqueNumberTracker();
        Scanner scanner = new Scanner(System.in);
        
        System.out.println("--- First Unique Number Tracker ---");
        System.out.print("Enter numbers separated by spaces (e.g., 4 5 4 6 5 7): ");
        
        // Read the entire line of input at once
        String inputLine = scanner.nextLine();
        
        // Split the string by whitespace to extract individual number strings
        String[] tokens = inputLine.trim().split("\\s+");
        
        // Process each number
        for (String token : tokens) {
            if (!token.isEmpty()) {
                try {
                    int num = Integer.parseInt(token);
                    tracker.add(num);
                } catch (NumberFormatException e) {
                    System.out.println("Skipping invalid entry: '" + token + "' (not a valid integer).");
                }
            }
        }
        
        // Print the final result
        int unique = tracker.getFirstUnique();
        if (unique != -1) {
            System.out.println("\nFinal Result -> The first unique number is: " + unique);
        } else {
            System.out.println("\nFinal Result -> No unique number exists in the stream (-1).");
        }
        
        scanner.close();
    }
}

```
## Output:


<img width="737" height="600" alt="image" src="https://github.com/user-attachments/assets/6399530b-d0e8-4d37-a87d-703308ebd150" />


## Result:
The program successfully tracks and returns the first unique number at any point in the integer stream using a LinkedHashMap.





















# Ex15 Value Existence Check in a TreeMap
## DATE: 01.09.2026
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

<img width="1041" height="722" alt="image" src="https://github.com/user-attachments/assets/13e11a9d-985c-4d86-8faa-0325beadcafc" />




<img width="732" height="462" alt="image" src="https://github.com/user-attachments/assets/c42a5ce4-c0d1-447a-9ebb-ed5527867c19" />


## Result:
Thus, the program successfully checks whether a specified value exists in a TreeMap using the containsValue() method.

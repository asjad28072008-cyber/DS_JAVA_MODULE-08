# Ex11 Convert HashSet to ArrayList in Java
## DATE:
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

<img width="670" height="467" alt="image" src="https://github.com/user-attachments/assets/4fe3e671-95d6-4dd4-868d-572eb37fc56d" />


## Result:
The program successfully converts a collection of distinct integers stored in a HashSet into an ArrayList

# Ex14 Tracking the First Unique Number in a Stream using LinkedHashMap
## DATE:
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

<img width="908" height="320" alt="image" src="https://github.com/user-attachments/assets/a11d051d-c8d6-41bf-9d95-be7d1a60d07d" />


<img width="885" height="248" alt="image" src="https://github.com/user-attachments/assets/6745106d-7398-41d9-b259-76ac7ccdcd8a" />


## Result:
The program successfully tracks and returns the first unique number at any point in the integer stream using a LinkedHashMap.

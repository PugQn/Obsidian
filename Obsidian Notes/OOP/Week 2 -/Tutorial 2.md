## Task 1

### Question 1
*What is the main difference between a while loop and a do…while loop?*

The while loop will only run if the condition is correct. The do...while loop will run then check the condition to see if it should run again.

### Question 2
*Write a for loop that will print out all the multiples of 3 from 3 to 36, that is: 3 6 9 12 15 18 21 24 27 30 33 36*

```
package week2;  
  
public class multiplesOf3 {  
    public static void main(String[] args) {  
  
        for (int i = 1; i < 13; i++) {  
            System.out.print(3 * i + " ");  
        }  
    }  
}
```

### Question 3
*Suppose that numbers is an array of type int[ ]. Write a code segment that will count and output the number of times that the number 42 occurs in the array.*

```
package week2;  
  
public class countOf42 {  
    public static void main(String[] args) {  
        int count = 0;  
        int[] group = {42, 1 , 2, 3, 42, 42};  
  
        for (int i = 0; i < group.length; i++) {  
            if (group[i] == 42) {  
                count++;  
            }  
        }  
        System.out.println(count);  
    }  
}
```

## Task 2

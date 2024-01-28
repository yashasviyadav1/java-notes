## How to take array as input when array size is not given

Input :
```java
1 2 3 4 5
```
Output : 
```java
integer array : 1 2 3 4 5 
```

code 
```java

public class Main {
    public static void main(String[] args) {
        
        // input : 1 2 3 4 5
        Scanner scn = new Scanner(System.in);
        String inputStr = scn.nextLine();
        String[] inputArr = inputStr.split(" ");
        int arr[] = new int[inputArr.length];
        for(int i=0; i < arr.length; i++)
            arr[i] = Integer.valueOf(inputArr[i]);
        
        System.out.print("integer array : ");
        for(int i=0; i<arr.length; i++)
            System.out.print(arr[i] + " ");
        // Output : integer array : 1 2 3 4 5 
    }
}
```
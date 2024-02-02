#### String to character array
```java
public class StringToCharArrayExample{  
   public static void main(String args[]){  
      String s1="hello";  
      char[] ch=s1.toCharArray();  
   }  
}  
// h, e, l, l, o, 
```

#### Char Array to String 

```java
char[] a = {'h', 'e', 'l', 'l', 'o', ' ', 'w', 'o', 'r', 'l', 'd'};
String str = new String(a);

//or

String str1 = String.valueOf(a);
```
#### String to int 
```java
String str = "1234"
int num = Integer.valueOf(str);
      OR 
int num2 = Integer.parseInt(str);


```
#### Integer to String
```java
Integer num = 1234;
String str = String.valueOf(num); // "1234"
```

#### Imp Asci ranges 
```java

A-Z (65-90) 
a-z (97-128)
0 to 9 (48-57)    or use Character.isDigit(ch)

```

#### Double to Integer 
```java
// normal
double data = 3452.345
int value = (int)data;  // 3452

// wrapperclass
double doubleNum = 123456789074
Integer intNum = doubleNum.intValue(); 

// (this way only those much digits fetched from double which are possible)


```
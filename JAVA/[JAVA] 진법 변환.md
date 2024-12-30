# [JAVA] 진법 변환   

1. 10진수 -> 2진수   
```java  
Integer.toBinaryString(num);    
```
- 해당 메서드를 사용하면 10진수를 2진수 문자열로 변환할 수 있다.

```java  
public class example {
  public static void main(String[] args) {    
    int number = 51;
    String binaryNum = Integer.toBinaryString(51);
  }    
}    
```    
    
2. 10진수 -> N진수       
```java   
Integer.toString(int num, int radix)   
```   
- 변환하고 싶은 n진수를 radix에 넣는다.
- 10진수를 제외한 나머지 진수는 String으로 받아야한다.
(int는 모두 10진수로 인식하기 때문에)    
- 8진수는 toOctalString, 16진수는 toHexString 메서드를 사용할 수 있다.    

```java   
public class example {
  public static void main(String[] args) {
    int num = 51;
    System.out.println("10진수 -> 3진수 : " + Integer.toString(num, 3)); // 10진수 -> 3진수    
    System.out.println("10진수 -> 5진수 : " + Integer.toString(num, 5)); // 10진수 -> 5진수    
    System.out.println("10진수 -> 8진수 : " + Integer.toString(num, 8)); // 10진수 -> 8진수    
  }    
}     
```

3. N진수 -> 10진수
```java
Integer.parseInt(String s, int radix);
```    
- n진수 값을 String s 변수에 넣고, 넣은 s값이 몇 진수 값인지 radix에 넣어야한다.    

```java   
public class example {
  public static void main(String[] args) {
    String s = 51;
    System.out.println("3진수 -> 10진수 : " + Integer.parseInt(s, 3)); // 3진수 -> 10진수    
    System.out.println("5진수 -> 10진수 : " + Integer.parseInt(s, 5)); // 5진수 -> 10진수    
    System.out.println("8진수 -> 10진수 : " + Integer.parseInt(s, 8)); // 8진수 -> 10진수    
  }    
}     
```

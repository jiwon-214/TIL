# [프로그래머스] 직사각형 별찍기_JAVA
### 문제 설명
---------------------------------------------
이 문제에는 표준 입력으로 두 개의 정수 n과 m이 주어집니다.   
별 문자를 이용해 가로의 길이가 n, 세로의 길이가 m인 직사각형 형태를 출력해보세요.

### 제한사항
----------------------------------------------
* n과 m은 각각 1000 이하인 자연수입니다.
* 
### 입출력 예
-----------------------------------------------
![io2](https://user-images.githubusercontent.com/59613778/158664465-46ca5bf4-55bc-41a9-8a54-2be0fe0000de.JPG)   

### 문제 풀이   
```java
import java.util.Scanner;

class Solution {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int a = sc.nextInt();
        int b = sc.nextInt();
        
        for (int i = 0; i < b; i++) {
            for (int j = 0; j < a; j++) {
                System.out.print('*');
            }
            System.out.println();
        }
    }
}
```

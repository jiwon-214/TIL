# [프로그래머스] 평균 구하기_JAVA
### 문제 설명
---------------------------------------------
정수를 담고 있는 배열 arr의 평균값을 return하는 함수, solution을 완성해보세요.   

### 제한사항
----------------------------------------------
* arr은 길이 1 이상, 100 이하인 배열입니다.   
* arr의 원소는 -10,000 이상 10,000 이하인 정수입니다.   

### 입출력 예
-----------------------------------------------
![ct2](https://user-images.githubusercontent.com/59613778/156870549-903ce836-581a-420a-96af-143359f03bd5.JPG)   

### 문제 풀이   
```java
class Solution {
    public double solution(int[] arr) {
        double sum = 0;
        double answer = 0;
        for (int i = 0; i < arr.length; i++) {
            sum += arr[i];
        }
        answer = sum / arr.length;
        return answer;
    }
}
```

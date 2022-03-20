# [프로그래머스] 약수의 개수와 덧셈_JAVA
### 문제 설명
---------------------------------------------
두 정수 left와 right가 매개변수로 주어집니다.   
left부터 right까지의 모든 수들 중에서, 약수의 개수가 짝수인 수는 더하고, 약수의 개수가 홀수인 수는 뺀 수를 return 하도록 solution 함수를 완성해주세요.     

### 제한사항
----------------------------------------------
* 1 ≤ left ≤ right ≤ 1,000   

### 입출력 예
-----------------------------------------------
![io3](https://user-images.githubusercontent.com/59613778/159160894-48e4b82a-d7c7-41fc-b932-a9ee04f8cf7d.JPG)   

### 입출력 예 설명
------------------------------------------------
입출력 예 #1   
* 다음 표는 13부터 17까지의 수들의 약수를 모두 나타낸 것입니다.   
![io4](https://user-images.githubusercontent.com/59613778/159160889-aac2487e-aa3f-4e7c-bddc-ca0f754aa397.JPG)   
* 따라서, 13 + 14 + 15 - 16 + 17 = 43을 return 해야 합니다.   
   
입출력 예 #2   
* 다음 표는 24부터 27까지의 수들의 약수를 모두 나타낸 것입니다.   
![io5](https://user-images.githubusercontent.com/59613778/159160891-296e96ca-0ce5-4f27-bc53-fa9b14ef9b1d.JPG)   
* 따라서, 24 - 25 + 26 + 27 = 52를 return 해야 합니다.   
   
### 문제 풀이   
```java
class Solution {
    public int solution(int left, int right) {
        int answer = 0;
        for (int i = left; i <= right; i++) {
            int count = 0;
            
            for (int j = 1; j <= i; j++) {
                if (i % j == 0) {
                    count++;
                }
            }
            
            if(count % 2 == 0) {
                answer += i;
            }
            else {
                answer -= i;
            }
        }
        return answer;
    }
}
```

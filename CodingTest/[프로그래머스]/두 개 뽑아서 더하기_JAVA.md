# [프로그래머스] 두 개 뽑아서 더하기_JAVA
### 문제 설명
---------------------------------------------
정수 배열 numbers가 주어집니다.   
numbers에서 서로 다른 인덱스에 있는 두 개의 수를 뽑아 더해서 만들 수 있는 모든 수를 배열에 오름차순으로 담아 return 하도록 solution 함수를 완성해주세요.   

### 제한사항
----------------------------------------------
* numbers의 길이는 2 이상 100 이하입니다.   
  * numbers의 모든 수는 0 이상 100 이하입니다.   
   
### 입출력 예
-----------------------------------------------
![io1](https://user-images.githubusercontent.com/59613778/158523999-82e084c8-bfcd-4e07-a1bc-85ad8a2bfe38.JPG)   

### 입출력 예 설명
------------------------------------------------
입출력 예 #1   
   
2 = 1 + 1 입니다. (1이 numbers에 두 개 있습니다.)   
3 = 2 + 1 입니다.   
4 = 1 + 3 입니다.   
5 = 1 + 4 = 2 + 3 입니다.   
6 = 2 + 4 입니다.   
7 = 3 + 4 입니다.   
따라서 [2,3,4,5,6,7] 을 return 해야 합니다.   
   
입출력 예 #2   
   
2 = 0 + 2 입니다.   
5 = 5 + 0 입니다.   
7 = 0 + 7 = 5 + 2 입니다.   
9 = 2 + 7 입니다.   
12 = 5 + 7 입니다.   
따라서 [2,5,7,9,12] 를 return 해야 합니다.   

### 문제 풀이   
#### 1. ArrayList 사용
```java
import java.util.*;

class Solution {
    public int[] solution(int[] numbers) {
        ArrayList<Integer> list = new ArrayList<Integer>();
        
        for (int i = 0; i < numbers.length; i++) {
            for (int j = i + 1; j < numbers.length; j++) {
                int n = numbers[i] + numbers[j];
                
                if(list.indexOf(n) < 0) {
                    list.add(n);
                }
            }
        }
        
        int[] answer = new int[list.size()];
        
        for (int i = 0; i < list.size(); i++) {
            answer[i] = list.get(i);
        }
        Arrays.sort(answer);
        return answer;
    }
}
```
> indexOf()는 특정 문자나 문자열이 앞에서부터 처음으로 발견되는 인덱스를 반환하며, 찾지 못했을 경우에는 -1을 반환한다.     

#### 2. HashSet 사용
```java
import java.util.*;

class Solution {
    public int[] solution(int[] numbers) {
        HashSet<Integer> set = new HashSet<Integer>();
        
        for (int i = 0; i < numbers.length; i++) {
            for (int j = i + 1; j < numbers.length; j++) {
                set.add(numbers[i] + numbers[j]);
            }
        }
        return set.stream().sorted().mapToInt(Integer::intValue).toArray();
    }
}
```

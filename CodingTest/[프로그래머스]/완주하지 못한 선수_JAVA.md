# [프로그래머스] 완주하지 못한 선수_JAVA
### 문제 설명
---------------------------------------------
수많은 마라톤 선수들이 마라톤에 참여하였습니다.   
단 한 명의 선수를 제외하고는 모든 선수가 마라톤을 완주하였습니다.   
마라톤에 참여한 선수들의 이름이 담긴 배열 participant와 완주한 선수들의 이름이 담긴 배열 completion이 주어질 때, 완주하지 못한 선수의 이름을 return 하도록 solution 함수를 작성해주세요.   

### 제한사항
----------------------------------------------
* 마라톤 경기에 참여한 선수의 수는 1명 이상 100,000명 이하입니다.   
* completion의 길이는 participant의 길이보다 1 작습니다.   
* 참가자의 이름은 1개 이상 20개 이하의 알파벳 소문자로 이루어져 있습니다.   
* 참가자 중에는 동명이인이 있을 수 있습니다.   

### 입출력 예
-----------------------------------------------
![ct1](https://user-images.githubusercontent.com/59613778/155381300-6711fb50-3820-4980-bcb6-88d4bd66d0fa.JPG)

### 입출력 예 설명
------------------------------------------------
예제 #1   
"leo"는 참여자 명단에는 있지만, 완주자 명단에는 없기 때문에 완주하지 못했습니다.   
   
예제 #2   
"vinko"는 참여자 명단에는 있지만, 완주자 명단에는 없기 때문에 완주하지 못했습니다.   
   
예제 #3   
"mislav"는 참여자 명단에는 두 명이 있지만, 완주자 명단에는 한 명밖에 없기 때문에 한명은 완주하지 못했습니다.   

### 문제 풀이   
#### 1. 배열 사용
```java
import java.util.Arrays;
class Solution {
    public String solution(String[] participant, String[] completion) {
        String answer = "";
        Arrays.sort(participant);
        Arrays.sort(completion);

        for(int i = 0; i < completion.length; i++) {
            if(!participant[i].equals(completion[i])) {
                return participant[i];
            }
        }
        return participant[participant.length - 1];
    }
}
```
이 문제에서 구해야 하는 것은 완주하지 못한 선수입니다.   
즉, completion 배열에는 존재하지 않으면서 participant 배열에는 존재하는 선수입니다.   
두 배열에서 일치하지 않는 요소가 완주하지 못한 선수이기 때문에,   
participant, completion 배열을 각각 정렬한 후, 반복문을 통해서 두 배열을 비교한 후, completion 배열의 요소와 일치하지 않는 participant 배열의 요소를 반환해주면 됩니다.   
반복문이 종료되었는데도 일치하지 않는 요소가 없었다면, participant 배열의 마지막 요소를 반환해줍니다.   

#### 2. HashMap 사용
```java
import java.util.HashMap;
class Solution {
    public String solution(String[] participant, String[] completion) {
        String answer = "";
        HashMap<String, Integer> hm = new HashMap<>();
        
        for(String player : participant) hm.put(player, hm.getOrDefault(player, 0) + 1);
        for(String player : completion) hm.put(player, hm.get(player) - 1);
        
        for (String key : hm.keySet()) {
            if(hm.get(key) != 0) {
                  answer = key;
            }
        }
        return answer;
   }
}
```
---
HashMap에 participant 배열 요소를 key 값으로 넣고, value는 1을 넣어줍니다.   
동일한 HashMap에 completion 배열 요소를 key 값으로 넣으면서 HashMap hm에 key 값이 존재한다면 value에서 1을 빼줍니다.   
이렇게 하면, 각 key 값의 value가 0이 아니라면 완주하지 못한 선수를 알 수 있습니다.   
key 값의 집합을 가져와서 value 값을 확인한 후, value가 0이 아닌 완주하지 못한 선수를 반환해줍니다.

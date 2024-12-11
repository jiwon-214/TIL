# [JAVA] String - split
------------------------
### split()
split() 메서드는 문자열을 특정 구분자를 기준으로 나누어 문자열 배열로 변환하는 메서드   
주로 문자열 처리에서 구분자를 기준으로 단어를 분리하거나 데이터를 가공하는 데 사용된다.   
구분자는 특수문자, 공백 및 정규식을 사용할 수도 있다.   

--------------------------
split(String regex, int limit)   
limit은 제외 가능   

```java
String[] result = inputString.split(String regex);   
String[] result = inputString.split(String regex, int limit);   
```
* regex: 문자열을 나누는 기준이 되는 정규식   
* limit(Optional): 배열의 최대 크기를 지정하는 매개변수
  * 양수: 최대 크기만큼 분리하며, 초과 부분은 그대로 반환
  * 0: 끝의 빈 문자열을 제거   
  * 음수: 빈 문자열도 결과 배열에 포함되며 끝의 빈 문자열도 포함하여 분리   

-----------------------------
### 기본 사용법   
1. 공백을 기준으로 분리   
```java
String inputString = "my favorite star"
String[] result = inpuitString.split(" ");

for (String word: result) {
  System.out.print(word);
}
```    
> 출력결과:   
> my   
> favorite    
> star    

2. 구분자를 기준으로 분리   
```java   
String inputString = "baseball,bat,swing"   
String[] result = inpuitString.split(",");   
    
for (String word: result) {   
  System.out.print(word);    
}   
```
> 출력결과:   
> baseball   
> bat    
> swing
        
3. 정규식을 기준으로 분리
```java   
String inputString = "abc123def456";   
String[] result = inpuitString.split("[^0-9]+"); // 숫자를 기준으로 분리   
    
for (String word: result) {   
  if(!word.isEmpty()) System.out.println(word); 
}   
```
> 출력결과:   
> 123   
> 456    

4. Pattern을 이용하여 문자열 분리
```java   
String inputString = "Americano Caffelatte Coke Water";
Pattern pattern = Pattern.compile("\\s"); //분리할 문자열의 패턴을 생성
String[] result = pattern.split(inputString);   
    
System.out.println(Arrays.toString(result));    
```
> 출력결과:   
> [Americano, Caffelatte, Coke, Water];   

---------------------------
### 사용 시 주의할 점
* ., *, |, ? 등은 정규식에서 특수한 의미를 가지므로 \\로 이스케이프가 필요하다.
```java
String input = "hello. future";
String[] result = input.split("\\.");
```

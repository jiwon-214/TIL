# [JAVA] String - split
------------------------
### split()
split() 메서드는 문자열을 특정 구분자를 기준으로 나누어 문자열 배열로 변환하는 메서드   
주로 문자열 처리에서 구분자를 기준으로 단어를 분리하거나 데이터를 가공하는 데 사용된다.   
구분자는 특수문자, 공백 및 정규식을 사용할 수도 있다.   

--------------------------
split(String regex, int limit)   
limit은 제외 가능   

'''JAVA
String[] result = inputString.split(String regex);   
String[] result = inputString.split(String regex, int limit);   
'''
> regex: 문자열을 나누는 기준이 되는 정규식   
> limit(Optional): 배열의 최대 크기를 지정하는 매개변수   
> > 양수: 최대 크기만큼 분리하며, 초과 부분은 그대로 반환   
> > 0: 끝의 빈 문자열을 제거   
> > 음수: 빈 문자열도 결과 배열에 포함되며 끝의 빈 문자열도 포함하여 분리   

-----------------------------
기본 사용법   
1. 공백을 기준으로 분리   
'''JAVA
String inputString = "my favorite star"
String[] result = inpuitString.split(" ");

for (String word: result) {
  System.out.print(word);
}
'''JAVA      
> 출력결과:   
> my   
> favorite    
> star    

2. 구분자를 기준으로 분리   
'''JAVA   
String inputString = "baseball,bat,swing"   
String[] result = inpuitString.split(",");   
    
for (String word: result) {   
  System.out.print(word);    
}   
'''JAVA 
> 출력결과:   
> baseball   
> bat    
> swing
        
3. 

#The file will have its original line endings in your working directory
=======================================================================
* 이것의 원인은 윈도우의 줄 바꿈 문자와 리눅스의 줄 바꿈 문자가 다르기 때문에 발생한다.
* 리눅스 시스템에서 개행 문제 또는 End of Line(EOL)을 Line Feed(LF)로 나타내며
윈도우 시스템에서는 Carriage Return(CR) 그리고 Line Feed(LF)를 합쳐 CRLF로 나타낸다.
* Git의 명령들은 리눅스를 기반으로 처리하므로 오직 Line Feed(LF)를 코드로 처리한다.
* 이 메시지는 윈도우에서 작업한 문서들의 CRLF 문자를 LF 문자로 변환해서 커밋할 것이라는 알림성 메시지이다.

* CRLF를 LF 문자로 변환해주기 위한 아래 명령어를 터미널에 쳐주면 해결이 가능하다.
> git config --global core.autocrlf true

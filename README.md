# study 코드트리 1일차
**출력**
------------------------------------

    #include <stdio.h>


    int main() {
    
        // Please write your code here.
        }
뭔가 printf(~);

출력 기본형이다~~ 이 구조는 알고 있자

**여기서 ";" 이거 까먹으면 안될듯!!**

**문자열 특수 문자 포함**
-------------------------------------------
여기서 많이 틀림
   
    #include <stdio.h>

    int main() {
    printf("He says \"It\'s a really simple sentence\".");
    return 0;
    }
여기서 ", !, 뭐 이런 특수 문자들을 **문자**로서 넣으려면 '\'가 필요함
    
    example) 
    printf("\"Hello"");
하면 "Hello"가 출력됨!!
He says "It's a really simple sentance".가 예제였음

**그럼 "랑 '가 특수문자임.**

**'.'는 특수문자 아님**

# study 코드트리 2일차
**줄바꿈**
-------------------------------------------
'\n' <----- 요녀석을 이용한다!!
이 녀석은 new line을 의미하는 특수문자!

    #include <stdio.h>

    int main() {
        printf("Hello World");
        printf("\n");
        printf("C is fun");
        return 0;
    }
하면  
Hello World  
C is fun  
이라고 나옴 









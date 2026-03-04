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
여기서 "나 뭐 이런 특수 문자들을 **문자**로서 넣으려면 '\'가 필요함
    
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
이라고 나옴 ***근데!!*** 저거 3줄 쓰는거 귀차늠
**고래서!!** ****'\n'이 문자열에 속할 수 있는 문자여서****

    #include <stdio.h>
    int main() {
        printf("Hello World\nC is fun");
        return 0;
    }
이렇게 해도 똑같은 출력값이 나옴

**숫자 출력**
-------------------------------------------
printf(3); 을 해버리면 애러가 뜬다;;
숫자 3을 출력하려면 ****""문자열 내에 변수 포맷(%d)를 지정해야 한다.****
=> printf("%d", 포맷에 대응하는 숫자 변수)

**BUT!!** 변수 포맷을 이용하지 않고도 출력은 가능

    #include <stdio.h>
    int main() {
        pinrtf("3");
        return 0;
    }
하면 숫자 3은 아니지만 어쨌거나 3은 나옴;; ㅋㅋ
***하지만!! 숫자 3은 아님!!***

**여러개 숫자 사이에 공백 채우기**
-------------------------------------------
이건 좀 이~~~zㅣ 했음

그냥 printf("3 5"); 해도  
출력값은 '3 5' 가 나온다

근데 변수 포맷을 쓴다?  
**printf("%d %d", 3, 5);** 이렇게 써야함  
그래야지 숫자 3과 5가 '3 5'와 같은 모양으로 나옴

# study 코드트리 3일차
**기본 활용 문제 풀이**
---------------------------------------------

    #include <stdio.h>

    int main() {
        printf("Total days in Year");
        printf("\n");
        printf("%d", 365);
        printf("\n");
        printf("Circumference rate");
        printf("\n");
        printf("%d", 3);
        printf(".");
        printf("%d", 1415926535);
        return 0;    
    }
이게 내 풀이인데 너무 비효율적인거 같음

    #include <stdio.h>

    int main() {
        printf("Total days in Year\n");
        printf("%d\n", 365);
        printf("Circumference rate\n");
        printf("%.10f", 3.1415926535);
        return 0;
    }
여기가 좀 더 나은 구조인거 같음!!

# study 코드트리 4일차
**변수와 자료형**
--------------------------------------------
변수 선언
    
    a = 5;
위의 코드대로라면, a라는 변수에 5라는 숫자가 들어가게 되는거임
정수: int, long long
실수: double
문자: char
문자열: char[]

정수, 실수에 해당하는 변수들 -> 더하고(+), 뺴고(-), 곱하고(*), 나누는(/)거 가능

*코딩 컨벤션*(Coding Convention)
: 일반적으로 변수나 함수명은 소문자로 쓰는 것이 원칙이며, 여러 단어를 사용하는 경우 언더바를 사용함
**정수 선언하고 뺄셈**
두 개의 정수형 변수를 선언하고 각각 97, 13값을 대입. 이 두 변수를 활용해 출력 형식에 맞게 뺄셈식을 출력

출력
:97 - 13 = 84
(띄어쓰기도 고려해야함)

    #include <stdio.h>
    int main() {
    int a=97, b=13;
    printf("%d - %d = %d", a, b, a-b);
    return 0;
    }
**변수 선언하기**
//c언어에서 ''는 문자, ""는 문자열을 나타낼 때 씀





















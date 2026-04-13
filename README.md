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
----------------------------------------------------
//c언어에서 ''는 문자, ""는 문자열을 나타낼 때 씀
//문자 변수는 %c로 출력하나봄

    #include <stdio.h>

    int main() {
    int a=3;
    char b='C';
    printf("%d\n", a);
    printf("%c", b);
    return 0;
    }

# study 코드트리 5일차
**출력형식**
-----------------------------------------
%s : 문자열  
%c : 문자  
%d : 정수  
%IF : 실수  
//4일차 참고  
정수: int, long long  
실수: double  
문자: char  
문자열: char[]

**예제1)**  
변수 a, b, c에 각각 1, 2, C를 넣어주고, 출력 형식에 알맞게 출력하는 프로그램을 작성  
출력: 1->2->C

    #include <stdio.h>

    int main() {
    int a=1;
    int b=2;
    char c[10]="C";
    printf("%d->%d->%s", a, b, c);
    return 0;
    }

**소수점 맞춰 출력**
---------------------------------------
%.nlf: 소수점 n쨰자리까지 값을 반올림해서 출력

예제1) 달에서 무게 구하기  
추의 무게 =13, 달에서 중력의 비율= 0.165  
출력: 13 * 0.165000 = 2.145000  

    #include <stdio.h>

    int main() {
    int a=13;
    double b=0.165;
    double c=a*b;
    printf("%d * %6lf = %6lf", a, b, c);
    return 0;
    }
예제2) 길이 단위 변환  
1피트 = 30.48cm, 1마일 = 160934cm  
9.2피트와 1.3마일을 각각 cm로 변환 및 소수 첫째자리까지 출력  
출력:  
9.2ft = 280.4cm
1.3mi = 209214.2cm

    #include <stdio.h>

    int main() {
    double a=9.2, b=1.3, c=a*30.48, d=1.3*160934;
    printf("%.1lfft = %.1lfcm\n", a, c);
    printf("%.1lfmi = %.1lfcm", b, d);
    return 0;
    }

# study 코드트리 6일차  
**변수 값 변경**
---------------------------------------------------  

    #include <stdio.h>
    int main() {
	int a = 5;
	printf("A is %d\n", a);

	a = 3;
	printf("A is %d", a);
	return 0;
    }
이렇게 되면 변수 a값이 처음엔 5로 설정됐지만 최종적으로 3이 나오게 된다.  
그리고 조금 틀어서  
예제1) 변수 a의 값에 다른 변수 b에 있는 값을 가져와 넣어주는 것도 가능함

    
    #include <stdio.h>
    int main() {

	int a = 5, b = 3;
	printf("A is %d\n", a);
	a = b;
	printf("A is %d\n", a);
	a = 2;
	printf("B is %d", b);
	return 0;
    }
결과값:  
A is 5  
A is 3  
B is 3

**두 변수 값을 교환**
--------------------------------------------------  
1) temp 이용

   		temp = a;
		a = b;
		b = temp;
이게 기본틀임. 이렇게 되면 *a랑 b에 있는 값이 스위치 된다*  

	
	#include <stdio.h>
	int main() {
    int a = 5, b = 3;
    int temp;

    temp = a;
    a = b;
    b = temp;

    printf("A is %d B is %d", a, b);
    return 0;
	}
결과값: A is 3 B is 5  
***근데!!!***  

	int temp;
	temp=a;
	=
	int temp=a;
2줄 쓸거 한 줄로 쓰는 방법도 있음  
예제1) 세 정수 a, b, c에 차례로 5, 6, 7을 넣고  
b에는 a값, c에는 b값, a에는 b값을 넣어 출력  

	#include <stdio.h>

	int main() {
    int a=5, b=6, c=7;
    int temp=a;
    a=c;
    c=temp;
    temp=b;
    b=c;
    c=temp;
    printf("%d\n%d\n%d", a, b, c);
    return 0;
	}
결과값:  
7  
5  
6  

	int a = 5, b = 6, c = 7;
    int temp = b;
    b = a;
    a = c;
    c = temp;
이 부분이 조금 더 간단한거 같아서 참고하면 좋을듯  

# study 코드트리 6일차  
**변수값 동시에 복사**
-----------------------------------------------------------  
변수 c에 담겨있는 값을 변수 a, 변수 b에 동시에 복사하는 방법!!  

	
	#include <stdio.h>
	int main() {
	int a = 5, b = 3, c = 9;
	a = b = c;
	printf("A is %d B is %d C is %d", a, b, c);
	return 0;
	}
출력값: A is 9 B is 9 C is 9  
=연산을 chain형시으로 적어주는것임  
그래서 b에 c값을 주고, a에 b값을 넣어주는 과정임  
이걸 이용해서 a = b = c = 0라는 코드로 a,b,c값을 동시에 전부 0으로 바꿀 수도 있음  

예제1) 합 복사  
-정수 a, b, c에 차례로 1, 2, 3을 넣는다
-세 정수의 합을 각 정수 a, b, c에 저장
-a, b, c의 값을 차례로 출력

	#include <stdio.h>
	int main() {
    int a=1, b=2, c=3;
    a=b=c=6;
    printf("%d %d %d", a, b, c);
    return 0;
	}
여기서 **a=b=c=a+b+c** 라고 해도 괜찮음  
변수값이 적어서 그냥 바로 6을 적었는데 **못 그럴 경우에** 수식쓰기  

**입력 함수 scanf**
------------------------------------------------------------------  
scanf라는 함수를 통해 공백 단위로 입력을 받을 수 있다  
scanf("변수 포맷", 변수의 주소);  
-> printf와는 다르게 변수가 아니라 변수의 주소를 써야함  
-> a라는 변수가 있다면, &a = 변수 a의 주소임  

	#include <stdio.h>
	int main() {
	int a;
	scanf("%d", &a);
	printf("%d", a);
	return 0;
	}
이게 기본 코드임  
변수 a를 선언하고 scanf 함수로 입력할 수 있는걸 만듬  

**실수 입력**
---------------------------------------------  
실수 포맷 = %lf  
변수 = double  
*앞에서 배웠던 %.nlf(소수점 n자리까지 반올림)*  
기본모형   

	#include <stdio.h>
	int main() {
    double a;
    scanf("%lf", &a);
    printf("%.2lf", a + 0.58);
    return 0;
	}

# study 코드트리 6일차  
**공백을 사이에 두고 입력 (변수&문자)**
--------------------------------------------------
변수를 공백을 끼워서 받는거는 맨 앞에서 다뤘음.  
ex) scanf("%d %d", &a, &b);  
라고 하면 되는건데 ***%d%d***라고 해도 될까?  
-> ㅇㅇ 가능함  
****BUT!!!!!!!!!**** 문자는 상관 있음  

	#include <stdio.h>
	int main() {
	char a, b;
	scanf("%c%c", &a, &b);
	printf("%c %c", a, b);
	return 0;
	}
출력값:  
a b  
a (공백)
이와 같이 b가 나와야 할 자리에 공백이 들어가게됨  
**따라서 만약 공백을 제외한 문자가 나올 때까지 입력으로 들어오는 모든 공백을 무시하고 싶다면, %c 앞에 공백을 넣어주면 됨  


문자열 선언:  
char a[15];  

	#include <stdio.h>
	int main() {
	char a[10], b[10];
	scanf("%s %s", a, b);
	printf("%s\n", a);
	printf("%s", b);
	return 0;
	}
>> abc def

abc  
def  
문자열의 경우 공백을 기준으로 구분이 이루어지기 때문에, %s%s로 받아도 공백이 무시되고 같은 결과가 나오는걸 확인할 수 있다  

# study 코드트리 7일차  
**문자열 입촐력**
---------------------------------------------------
문자열은 char[] / %s 포맷이다.
다만 scanf에서 주소자리에 &기호를 쓰지 않는다.  
또한 int 나 double처럼 ***a, b; 와 같은게 먹히지 않는다.***  
**무조건 따로 선언**을 해야함!!  

**문자열 입촐력**
----------------------------------------------------------------------
두 수가 공백이 아닌 특정 문자를 사이에 두고 입력으로 들어가는 경우에는 다음과 같이 scanf 안의 문자열 내에서 그 특정 문자를 받아주어야 한다.

	#include <stdio.h>

	int main() {
    int h, m;
    scanf("%d:%d", &h, &m);
    printf("%d:%d", h+1, m);
    return 0;
	}
**여기서!! 왜 : 를 scanf에 넣었냐면**  
입력 형식이 10:30 으로 고정되어 있기 때문이다.  
알고리즘 문제에서 입력 형식이 10:30 처럼 주어지면, scanf에 "%d:%d" 로 쓰면 콜론을 자동으로 무시하고 h=10, m=30 으로 파싱해준다.  
하지만 그 반대일 경우, 파싱에 실패함.  

# study 코드트리 8일차  
**사칙연산**
---------------------------------------------------
덧셈 / +  
뺄셈 / -  
곱셈 / *  
나눗셈 몫 -> /  
나눗셈 나머지 -> %  

**사칙연산 다른 표현법**
---------------------------------------------------
변수 a에 현재 들어 잇는 값에 5만큼을 주는 경우  
-> a = a + 5;  
라고 해도 됨. or a += 5;  

# study 코드트리 9일차  
**합과 차의 나눗셈**
---------------------------------------------------
두 정수 a, b가 주어질 때, 두 수의 합을 차로 나눈 값을 반올림하여 소수점 둘째 자리까지 출력하는 프로그램  
1.내 답안

	#include <stdio.h>

	int main() {
    double a, b, sum, m;
    scanf("%lf %", &a, &b);
    sum = a + b;
    m = a - b;

    printf("%.2lf", sum / m);
    return 0;
	}

2. 해설

		#include <stdio.h>
	
		int main() {
	    // 변수 선언 및 입력
	    int a, b;
	    scanf("%d %d", &a, &b);
	    
	    printf("%.2lf\n", (double)(a + b) / (a - b));
	    return 0;
		}
해설과 내 답안의 차이점  
: 나는 변수를 double로 설정햇고, 해설은 int로 설정하고 계산할 때 double을 씀  


**if문**
---------------------------------------------------
if (조건) {  
여기에 조건이 참일 경우에만 수행되는 코드 작성  
}  
'==' 기호는 값 뿐만 아니라 type도 일치해야 하기 때문에 1 == '1'은 false임  
문제.  
정수 n을 입력 받아 첫째줄에는 입력받은 정수를 출력하고  
그 정수가 음수일 경우에는 두번째줄에 minus를 출력함.  
1.내 답안

	#include <stdio.h>

	int main() {
    int n;

    scanf("%d", &n);

    if(n < 0)
        printf("%d\nminus", n);
    else
        printf("%d", n);
    return 0;
	}

2.해설

		#include<stdio.h>
	
		int main() {
	    // 변수 선언
	    int n;
	
		// 입력
		scanf("%d", &n);
	    
	    // 출력
		printf("%d\n", n);
		if(n < 0)
			printf("minus\n");
	    return 0;
		}
해설과 내 답안의 차이점  
: 입력 받고 그냥 출력을 함. **조건은 두번째 줄을 출력 하느냐 마느냐임으로  
해설의 답안이 더 효율적인거 같다**

**if문**
---------------------------------------------------
문제  
: 변수 두개를 선언해서 두 정수를 입력받아 연산을 하고, 연산값에 따라 추가적인 출력을 판단  
1. 내 답안

		#include <stdio.h>
	
		int main() {
	    int h, w;
	    double b;
	    
	    scanf("%d %d", &h, &w);
	    b = (10000 * w) / (h * h); 
	
	    printf("%.0lf\n", b);
	    if(b >= 25)
	    printf("Obesity");
	    return 0;
		}

2. 해설

   		#include <stdio.h>

		int main() {
	    // 변수 선언
	    int h, w;
	
	    // 입력
	    scanf("%d %d", &h, &w);
	    
	    // 키(cm)에서 키(m)로 단위 환산을 한 뒤 
	    // 체질량지수 계산 식에 넣어야 함에 유의합니다.
	    int bmi = w * 100 * 100 / (h * h);
	    
	    // 출력
	    printf("%d\n", bmi);
	    if(bmi >= 25)
	        printf("Obesity\n");
	    return 0;
		}

해설과 내 답안의 차이점:  
일단 변수는 2개만 설정해야함. double b; 를 설정한거에서 틀림.  
그리고 b를 int로 설정하고 계산하면 더 효율적이었을거임.  

**if else 조건문**
------------------------------------------
if (조건) {  
여기에 조건이 참일 경우에만 수행되는 코드 작성  
}  
else {  
여기에 조건이 거짓일 경우에만 수행되는 코드 작성  
}  
이 위치에 있는 코드는 조건과 무관하게 항상 수행됩니다.  

**삼항 연산자**
------------------------------------------
a = 조건 ? v1 : v2;  
a 조건이 참일 때 v1, 거짓일 때 v2가 나옴  

문제:  
정수 2개를 입력바아 두 값중 최댓값을 출력하는 프로그램을 작성해보세요.

1. 내 답안

		#include <stdio.h>
	
		int main() {
	    int a, b;
	
	    scanf("%d %d", &a, &b);
	
	    a = a > b ? a : b;
	    printf("%d", a);
	    return 0;
		}

2. 해설

	   	#include <stdio.h>
	
		int main() {
	    // 변수 선언
	    int a, b;
	
	    // 입력
	    scanf("%d %d", &a, &b);
	    
	    int maxnum = a > b ? a : b;
	    
	    // 출력
	    printf("%d\n", maxnum);
	    return 0;
		}
해설과 내 답안의 차이점:  
int maxnum을 설정하고 만드심.  















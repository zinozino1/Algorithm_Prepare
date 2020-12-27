```py

1. 변수와 출력 함수


* 변수명 정하기
1) 영문과 숫자, _로 이루어진다
2) 대소문자를 구분한다. a 와 A는 다름
a = 1
A = 2
print(a,A) => 1,2출력

3) 문자나, _로 시작한다
4) 특수문자, 키워드 사용하면 안됨


* 나열 하여 대입 가능

a, b, c = 10, 2, 1
print(a, b, c)
a, b, c = 1, 2, 3
print(a, b, c) --> 재할당 가능



* 값 교환

a, b = 10, 20
print(a, b) // 10, 20
a, b = b, a
print(a, b) // 20, 10



* 변수 타입

a = 12314 -> 4바이트
print(type(a))
print(a)

a = 123.123123123123 -> 8바이트
print(type(a))
print(a)

a = 1.123123123123123213131231 -> 8바이트
print(type(a))
print(a)

= 결과
<type 'int'>
12314
<type 'float'>
123.123123123
<type 'float'>
1.12312312312


a = "str" // string 싱글, 더블 따옴표 둘 다 가능
print(type(a))
<type 'str'>



* 출력방식

a, b, c = 1, 2, 3
print(a, b, c) // 1 2 3
print(a, b, c, sep=", ") // 1, 2, 3
print(a, b, c, sep=",") // 1,2,3
print(a, b, c, sep="\n") //
1
2
3
print(a, end=" ") -> print 는 기본적으로 줄바꿈을 한다.
print(b)
print(c) //
1 2
3




2. 변수 입력과 연산자

* 사용자 입력 받기

a = input() // 입력
print(a) // 출력

a = input("입력하세요 : ")
print(a)

a, b = input("두 숫자를 입력하세요").split() // 2 3
print(a + b) // 23 -> 문자로 입력이 되어서 붙어버린다

type 이 str임.


* 형변환

a, b = input("숫자를 입력하세요: ").split()
a = int(a) // int형
a = float(a) // float형
print(type(a))


a, b, c = map(int, input("숫자를 입력하세요: ").split()) // 한꺼번에 미리 형변환 map 함수 이용
print(a, b, c)
-> 띄어쓰기 입력밖에?


* 연산

a, b = map(int, input("숫자를 입력하세요: ").split())

입력 : 10 2

print(a + b)
print(a - b)
print(a * b)
print(a / b) // 나누기 -> 5.0
print(a // b) // 몫 -> 5
print(a % b) // 나머지 -> 0
print(a ** b) // 거듭제곱 -> 100



a = 4.3
b = 5
c = a + b // 실수 + 정수 = 실수(더 큰 범위가 나옴)
print(type(c))





3. 조건문

* 조건

x = 7

if x == 7:
    print("같습니다")
    print("히히")
else:
    print("키키")

// 중괄호가 없음. 들여쓰기 신경써야함, 콜론 주의


* 논리 및 비교 연산자 활용
x = 7
if x > 0 and x < 10 and type(x) == int:
    print("10보다 작은 자연수") // "&& == and" "|| == or"


* 더 쉬운 방법. 파이썬만 되는 미친 문법
x = 7
if 0 < x < 7 and type(x) == int:
    print("zlzl")


* 분기

x = -10

if x > 0:
    print("양수")
else:
    print("음수")


* 다중 if

x = 93

if x >= 90: // A,B,C 다 출력하지 않는다. if elif 문의 특징
    print("A")
elif x >= 80:
    print("B")
elif x >= 70:
    print("C")
else:
    print("F")




4. 반복문

* range 함수

a = range(10) // 순차적으로 정수 리스트를 만듦 0부터 range - 1까지
print(list(a)) // [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]

a = range(1, 10) // 앞에 숫자는 포함 뒤에 숫자는 -1
b = range(1, 11)
print(list(a)) // [1, 2, 3, 4, 5, 6, 7, 8, 9]
print(list(b)) // [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]



for i in range(5): // 콜론 넣어주기 주의
    print("heelo", end=" ") // heelo heelo heelo heelo heelo

for i in range(1, 10):
    print(i) // 1부터 9까지 줄바꿈 출력

for i in range(10):
    print(i) // 0부터 9까지 줄바꿈 출력


* 역순

for i in range(10, 0): // 아무것도 출력 x
    print(i)

for i in range(10, 0, -1): // 10, 9, 8...
    print(i)

for i in range(10, 0, -2): // 10, 8, 6...
    print(i)


* while

i = 10

while i >= 1:
    print(i)
    i -= 1 // 파이썬에는 증감 연산자 없음


i = 1

while True: // 무한 루프
    print(1)

i = 1

while True: // break 는 다른 언어와 동일
    if i > 10:
        break
    print(i)
    i += 1

for i in range(1, 11): // continue 도 마찬가지
    if i % 2 == 0:
        continue
    print(i)



* for else 문

for i in range(1, 11):
    print(i)
    if i == 5:
        break
else: // for 문이 break 에 의해 종료되었다면 else문 실행 x
    print(11)

for i in range(1, 11):
    print(i)
    if i > 15:
        break
else: // for문이 다 돌았다면(정상적으로 돌았다면) else문 실행
    print(11)


```

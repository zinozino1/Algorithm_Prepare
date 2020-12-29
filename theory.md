```py

1. 변수와 출력 함수


* 변수명 정하기
1) 영문과 숫자, _로 이루어진다
2) 대소문자를 구분한다. a 와 A는 다름
a = 1
A = 2
print(a,A) => 1 2 출력

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

파이썬의 내장 함수인 map()는 여러 개의 데이터를 한 번에 다른 형태로 변환하기 위해서 사용됩니다. 따라서, 여러 개의 데이터를 담고 있는 list나 tuple을 대상으로 주로 사용하는 함수입니다.

사용 방법은 매우 간단한데요… 기본 문법은 다음과 같습니다.

map(변환 함수, 순회 가능한 데이터)

*** 하나만 변환할거면 int(input()) 이런식으로.


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


* 지수표현

1e9 = 1000000000   ~> 10억


* 반올림

round(실수형 데이터, 반올림하고자 하는 위치 -1)
round(423.456, 2)  ~> 423.46



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

a = range(1, 10) // 앞의 숫자는 포함 뒤의 숫자는 -1
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





5. 반복문을 이용한 문제 풀이

n = int(input())


1) 1부터 N 까지 홀수 출력

for i in range(1, n):
    if i % 2 == 0:
        continue
    print(i)

2) 1부터 N 까지의 합 구하기

sum = 0
for i in range(1, n + 1):
    sum += i
print(sum)

3) N의 약수 출력하기

for i in range(1, n + 1):
    if n % i != 0:
        continue
    print(i)





6. 중첩 반복문

별찍기.




7. 문자열과 내장 함수

str = "Time is Now!"

0) 간단한 문자열 연산

a = "Hello"
b = "World"
print(a + " " + b) ~> Hello World

a = "String"
print(a * 3) ~> StringStringString

1) 대문자화 - str.upper()
-> side effect x

2) 소문자화 - str.lower()
-> side effect x

3) 문자 찾기 - str.find(문자, [,index])
-> side effect x

4) 문자 들어간 갯수 - str.count(문자)
-> side effect x

5) 문자열 슬라이스 - str[[,숫자1]:숫자2]
-> side effect x
* 숫자1번째 인덱스부터 숫자2 - 1 까지 슬라이스 숫자1 없으면 0부터

6) 문자열 길이 - len(str)
-> side effect x
for i in range(len(str)):
    print(str[i])

for i in str: // 응용
    print(i, end="")

for i in str: // 응용 - 대문자만 출력
    if i.isupper():
        print(i)

for i in str: // 응용 - 공백 제거(알파벳만 출력)
    if i.isalpha():
        print(i, end="")

tmp='AZ' // 응용 아스키 코드 출력
for x in tmp:
    print(ord(x))

<->

tmp = 65
print(chr(tmp)) // 아스키 코드를 문자로






8. 리스트와 내장함수 (1)

리스트 - 파이썬의 배열


-> 리스트 선언법
a = [1,2,3] // [1,2,3]
b = list() // []


a = [1,2,3,4]
b = list(range(1,10))
c = a + b
print(c) // a와 b가 합쳐짐 미친문법


* 내장 함수

변수명.append()	리스트에 원소 삽입	| O(1)
변수명.sort()	오름차순으로 정렬	| O(NlogN)
변수명.sort(reverse=True)	내림차순으로 정렬	| O(NlogN)
변수명.reverse()	원래 원소의 순서를 뒤집어 놓음 | O(N)
변수명.insert(인덱스, 삽입할 값)	지정한 위치에 원소 삽입 | O(N)
변수명.count(특정 값)	특정한 값을 가지는 데이터의 개수	| O(N)
변수명.remove(특정 값)	특정한 값을 갖는 원소 제거	| O(N)

1) 리스트에 원소 추가 - arr.append(원소)
-> side effect o
-> 제일 뒤에 추가됨

2) 리스트의 특정 위치에 원소 추가 - arr.insert(인덱스, 원소)
-> side effect o

3) 리스트의 특정 위치 원소를 제거 - arr.pop([,인덱스])
-> side effect o
-> 빼낸 값을 활용 가능(변수 할당하여)
-> 인덱스 안 쓰면 리스트의 맨 뒤 원소 제거

4) 리스트의 특정 원소 제거 - arr.remove(리스트에 존재하는 원소)
-> side effect o

5) 리스트의 특정 원소 인덱스 알기 - arr.index(리스트에 존재하는 원소)
-> side effect o

6) 리스트 요소 모두 더하기 - sum(arr)
-> side effect x
-> 정수형 리스트만 가능한듯

7) 리스트 요소 중 최댓값 구하기 - max(arr)
-> side effect x

8) 리스트 요소 중 최솟값 구하기 - min(arr)
-> side effect x
-> min(1,2,3) // 1 - 인자값 중 최솟값


* import random as r // 랜덤 모듈 임포트 - 'r'로 사용하면 됨

a = list(range(1, 11))
r.shuffle(a) // 무작위 리스트 요소 출력


9) 리스트 정렬 - arr.sort([,reverse])
-> side effect o

a.sort() // 오름차순
a.sort(reverse=True) // 내림차순

10) 리스트 초기화(모든 요소 삭제) - arr.clear()
-> side effect o





9. 리스트와 내장함수 (2)

1) 리스트 슬라이스 - arr[[,숫자1]:숫자2]
-> side effect x
-> 문자열과 같음

2) 리스트의 길이 - len(arr)
-> side effect x
-> 문자열과 같음



* for문과 리스트의 활용

a = [11, 12, 35, 21, 36, 90]

for i in a: // 문자열과 같음 이게 훨씬 좋음
    print(i, end=" ")

for i in range(len(a)): // 문자열과 같음
    print(a[i], end=" ")

for x in enumerate(a): // 원소를 튜플 형태로 출력 (x가 튜플임)
    print(x)

(0, 11) // (인덱스, 원소값)
(1, 12)
(2, 35)
(3, 21)
(4, 36)
(5, 90)



* Tuple
그래프 알고리즘 구현시 자주 사용

다익스트라 최단 경로 알고리즘처럼 최단 경로를 찾아주는 알고리즘의 내부에서는 우선순위 큐를 이용하는데 해당 알고리즘에서 우선순위 큐에 한 번 들어간 값은 변경되지 않는다. 그래서 그 우선순위 큐에 들어가는 데이터를 튜플로 구성하여 소스코드를 작성한다.
또한, 튜플은 리스트에 비해 상대적으로 공간 효율적이고, 일반적으로 각 원소의 성질이 서로 다를 때 사용한다.
흔히 다익스트라 최단 경로 알고리즘에서는 '비용'과 '노드 번호'라는 서로 다른 성질의 데이터를 (비용, 노드번호)의 형태로 함께 튜플로 묶어서 관리하는 것이 관례이다.



a = (1,2,3,4,5)
print(a) // (1, 2, 3, 4, 5)
print(a[4]) // 5

** 리스트와 유사하나 튜플은 값을 변경할 수 없다

a[0] = 10 // error


a = [11, 12, 35, 21, 36, 90]
for x in enumerate(a): // tuple로 변경
    print(x[0], x[1]) // 0 11 1 12 2 35 3 21 4 36 5 90

for i, v in enumerate(a): // 더 자주 쓰이는 방법
    print(i, v)




* all 함수 - 리스트에 조건걸 때 유용

if all(100 > x for x in a): // 리스트의 모든 요소가 조건을 만족할 때
    print("모든 리스트 요소가 만족합니다.")
else:
    print("하나라도 만족 못하면 이리 옵니다.")

* any 함수 - 하나라도 만족할 떄

if any(100 > x for x in a):
    print("하나라도 만족합니다.")
else:
    print("모두 만족 못하면 이리 옵니다.")




10. 2차원 리스트 생성과 접근

* 리스트컴프리헨션
리스트를 생성하는 컴프리헨션을 리스트컴프리헨션 이라고 부릅니다.

a = [x for x in range(10)]
b = [1 for _ in range(10)]
c = [list(range(3)) for _ in range(3)]
d = [i for i in range(20) if i % 2 == 1]
e = [ 2 * x for x in range(1, 10 + 1) ]
e2 = [ x for x in range(10) if x < 5 if x % 2 == 0 ]
f = [ (x, y) for x in ['쌈밥', '치킨', '피자'] for y in ['사과', '아이스크림', '커피']]
g = [ (x, z, y) for x in ['쌈밥', '치킨', '피자'] for y in ['사과', '아이스크림', '커피'] for z in ['배달 시키기', '가서 먹기']]



a = [0] * 10 // 미친문법
print(a) // [0, 0, 0, 0, 0, 0, 0, 0, 0, 0]

a = [[0] * 3 for _ in range(3)]
print(a) // [[0, 0, 0], [0, 0, 0], [0, 0, 0]]


for i in a: // 자주 사용되는 2차원 리스트 출력법(행렬처럼)
    print(i)

for i in a: // 위 코드를 세분화
    for j in i:
        print(j, end=" ")
    print()

```

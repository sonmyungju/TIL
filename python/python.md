출처 : https://wikidocs.net/book/2

## 0. 준비
python.org 웹사이트에서 바로 작성 가능\
pythontutor.com 단계별로 실행 가능
## 1. 파이썬 시작하기
// 몫  
% 나머지
>#### divmod
```python
divmod(50,8)
```
(6,2)
>#### len
```python
onetofour = ['one','two','three','four']
len(onetofour)
```
4  
리스트에서 마지막 항목 뒤에 ,를 하나 더써도 무방하다.  

>#### pop
```python
onetofour.pop()
```
'four'  
마지막 값을 반환하고 제거, pop(1)등으로 지정 가능  
pop은 인덱스, remove는 지정한 값
```python
print(onetofour)
```
['one', 'two', 'three']
>#### remove
```python
onetofour.remove('two')
```

인터프리터(interpreter) : runs slowly, starts right away  
컴파일러(compiler) : runs very quickly, extra preparation time  

## 2. 제어 구조 (While/If/For/Match)
```python
i = 1
while i <= 3:
    print(i)
    i = i + 1
```
1  
2  
3
>#### round
````python
round(1,23456, 2)
````
1.23  
2.675 반올림시 2.67으로 계산되니 참고
* 숫자 뒤집기 예시

```python
num = 358
rem = rev = 0
while num >= 1:
    rem = num % 10
    rev = rev * 10 + rem
    num = num // 10
print(rev)
```
853
```python
max = 10
while True:
    num = int(input())
    if num > max:
        print(num, 'is too big')
        break
```
*14*  
14 is too big
>#### range
```python
for i in range(3):
    print(i)
```
0  
1  
2
>#### split
```python
'10 20'.split()
```
['10', '20']
* FizzBuzz 예시
```python
for n in range(1,7):
    match (n%3, n%5):
        case (0,0):
            print('FizzBuzz')
        case (0,_):
            print('Fizz')
        case (_,0):
            print('Buzz')
        case (_,_):
            print(n)
```
1  
2  
Fizz  
4  
Buzz  
Fizz  
## 3. 함수 (Def/Lambda/Map/Filter/Reduce)
```python
def quiz():
    ans = input('1 + 2 =')
    return 1 + 2 == int(ans)
```
*quiz()*  
1 + 2 =*3*  
True
>#### datetime
```python
from datetime import datetime
datetime.today()
```
datetime.datetime(2023, 1, 13, 0, 7, 11, 899962)  
```python
datetime.today().year
```
2023  

* 복리 계산 하는 법  
x 원을 3개월 동안 넣어두면 연 y의 이자를 주는 상품, 만기 때마다 재예치하여 n년 운용  
= x(1 + y/4) ** (4*n)

>#### 지역변수
```python
def e_is_10():
    global e
    e = 10
e_is_10()
e
```
10
>#### lambda
```python
def plus(x, y):
    return x + y
```
```python
(lambda x, y: x + y)(10, 20)
```
30  
여기서부터는 visual studio code로 작성하였음
>#### map
```python
square = list(map(lambda x: x**2, range(5)))
print(square)
```
```python
def sqr(x):
    return x**2
square = list(map(sqr,range(5)))
print(square)
```
[0, 1, 4, 9, 16]
>#### reduce  
```python
from functools import reduce

rev = reduce(lambda x, y: y + x, 'abcde')
print(rev)
```
'edcba'  
앞의 결과를 x에 다시 대입함.
>#### filter
```python
print(list(filter(lambda x: x < 3, range(10))))
```
[0, 1, 2]

>#### find
```python
print('175cm'.find('cm'))
```
3  
찾는 값이 없을 경우 -1을 반환한다.

* 예시 (map, strip, lambda, int 활용)
    ```python
    def read(text):
        ridename, limit= map(str.strip,text.split(':'))
        cmmin = cmmax = None
        if '~' in limit:
            cmmin, cmmax = map(lambda x: int(x.replace('cm','')),limit.split('~'))
        elif '이상' in limit:
            cmmin = int(limit.split('cm'))
        
        return ridename, cmmin, cmmax

    if __name__ == "__main__":
        ridename, cmmin, cmmax = read(input())
        print("이름:", ridename)
        print("하한:", cmmin)
        print("상한:", cmmax)
    ```
    *플라이 벤처: 140cm~195cm*  
    이름: 플라이 벤처  
    하한: 140  
    상한: 195  
## 4. 데이터 타입
>#### type
```python
print(type(6))
```
<class 'int'>
* 숫자 (numbers)
    * 정수 (int) : 6
    * 부동소수점수 (float) : 2.8
    * 복소수 (complex) : 3 + 4j
* 시퀀스 (sequence)
    * **문자열 (str)** <span style='background-color : #fff5b1'>*IMMUTABLE!*</span>
    * 리스트 (list)
    * 튜플 (tuple) <span style='background-color : #fff5b1'>*IMMUTABLE!*</span>
    * 사용자 정의 클래스  
    슬라이싱, for문에서 사용  
* 매핑 (mapping)
    * 딕셔너리 (dictionary)
* 불 (Bool) : True, False
* 세트 (Set) : {'apple', 'orange'}\
    원소의 순서가 유지되지 않고 중복 원소를 갖지 않음.  
>#### [ : : -1]
```python
print('Python'[::-1])
print('Python'[2::-1])
```
nohtyP  
tyP
>#### lower / upper
```python
print('PyTHon'.lower())
```
python
>#### replace
```python
print('Pethon'.replace('e','y'))
```
python

* 예시 회문(palindroma) 판단
    ```python
    def palindroma(text):
        text = text.lower()
        text = text.strip()
        return text == text[::-1]
    ```
    쓸데 없는 조건문 넣지 말고 return 값에 바로 주기

* 리스트
>#### append  

>#### sort

>#### insert

>#### del
```python
prime = [3, 5, 11]
prime.append(7)
print(prime)

prime.sort()
print(prime)

prime.insert(0,2)
print(prime)

del prime[4]
print(prime)
```
[3, 5, 11, 7]  
[3, 5, 7, 11]  
[2, 3, 5, 7, 11]  
[2, 3, 5, 7]
* 예시 소수 찾기
    ```python
    def find_prime(x):
        L = list(range(2,x))
        prime =[]

        for num in L:
            p = min(L)
            for num in L:
                if num % p == 0:
                    L.remove(num)
            prime.append(p)
        return prime
    ```
* 튜플  
ex) `(1, 2, 3)`, `1, 2, 3`, `()`  

* 딕셔너리  
ex) `{1 : '일', 2 : '이', 3 : '삼'}`  
>#### ord / chr
```python
print(ord('A'))
print(chr(65))
```
65  
A  
문자에 대응하는 코드값 / 코드값에 대응하는 문자
* 세트
>#### add
& 교집합  
| 합집합
## 5. 모듈


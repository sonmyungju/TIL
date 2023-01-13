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
>#### pop
```python
onetofour.pop()
```
'four'  
마지막 값을 반환하고 제거, pop(1)등으로 지정 가능
```python
print(onetofour)
```
['one','two','three']
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
14  
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
## 3. 함수 (Def/Lambda)
```python
def quiz():
    ans = input('1 + 2 =')
    return 1 + 2 == int(ans)
```
quiz()  
`1 + 2 =`3
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
>#### map


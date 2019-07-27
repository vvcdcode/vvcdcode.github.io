---
layout: post
title: Python function
date: 2019-07-13
tags: python basic
authors: gah_rlic
cover: /assets/post_image/20190628/test4.jpg
---

## 함수

### 함수의 기본 구조

def 함수명(매개변수):
<수행할 문장1>
<수행할 문장2>
...

    def add(a,b): #a, b는 매개변수
    	return a+b
    
    print(add(3,4)) #3,4 는 실행인자

    def print_root(a,b,c):     #(a,b,c)매개변수
    	r1 = (-b + (b ** 2 - 4 * a **c) ** 0.5) / (2 * a)
    	r2 = (-b + (b ** 2 - 4 * a **c) ** 0.5) / (2 * a)
        
    	print('해는 {} 또는 {}'.format(r1,r2))
        
    x = 1                      #실행인자
    y = 2
    z = -8

### 일반적인 함수

    def add(a,b):       # def 함수이름(매개변수):
    	result = a + b    # 수행할 문장
    	reutrn result     # return 결괏값
    
    a = add(3,4)        # 결괏값을 받을 변수 = 함수이름(수행인자1, 수행인자2 ...)
    print(a)
    7

    def add_10(value):
    	'''value 에 10을 더한 값을 돌려주는 함수'''
    	#return 10              을 하면 10의 값을 주고 뒷부분은 실행하지 않음. 즉시종료
    	result = value + 10
    	return result          #함수가 값을 갖도록 하는 기능
        
    n = add_10(42)           #add_10(42)만 쓰면 아무것도 출력 안됨
    print(n)                 #근데 이렇게 쓰면 52가 출력됨

입력값과 결괏값이 여러개인 경우

    def root(a,b,c): 
    	r1 = (-b + (b ** 2 - 4 * a **c) ** 0.5) / (2 * a)
    	r2 = (-b + (b ** 2 - 4 * a **c) ** 0.5) / (2 * a)
        
    	return r1, r2  # 갯수를 맞춰 쉼표로 구분만 해주면 여러개의 값을 반환할 수 있다
                         # 아까 같은경우는 여기에 바로 print를 썼지만 
                         # 지금은 return으로 값을 저장하고 그걸 함수로 부르면 되는것
        
    x= 1 
    y = 2
    z = -8
    
    r1, r2 = root(x,y,z)
    print('근은 {}'.format(r1, r2))

### 입력값이 없는 함수

    def say():          # () 입력값이 없다
    	return 'HI'       # return이 있어서 결괏값은 존재하는 것
    
    a = say()           # 결괏값을 받을 변수 = 함수이름()
    print(a)

### 결괏값이 없는 함수

    def add(a,b):
    	print('{},{}의 합은 {}입니다.'.format(a,b,a+b))  #이것은 결괏값이 아님
    
    add(3,4)            # 함수이름(수행인자1, 수행인자2...)
    3,4의 합은 7입니다.

### 입력값도 결괏값도 없는 함수

    def function():
    	print('안녕, 함수') #이것만 쓴상태로 실행하면 아무것도 출력하지 않음
        
    function()             #이것을 써야지만 함수가 호출, 실행된다
    안녕, 함수

### 함수의 초깃값

    def say_myself(name, old, woman=True):
    	print("나의 이름은 %s 입니다." % name)
    	print("나이는 %d 살입니다." % old)
    	if woman:
    		print("여자입니다.")
      else:
    	  print("남자입니다")
    
    say_myself("김갈릭", 25)
    say_myself("김갈릭", 25, True)
    
    나의 이름은 김갈릭입니다.
    나이는 25 살 입니다.
    여자입니다.
    
    # 여기서 조심해야하는 것은 woman=True 와 같은 초깃값은 항상 뒤쪽에 놔야한다. 
    # def say_myself(name, woman=True, old)의 순서는 안된다는 것!

### round 함수

    def print_round(number): 
    	 rounded = round(number)     #반올림 해주는 함수
    	 print(rounded)
        
    print_round(4.6)
    5
    print_round(2.2)
    2

### 연습문제 1

주어진 자연수가 홀수인지 짝수인지 판별해주는 함수(is_odd)를 작성해 보자.

    def is_odd(number):
        #number = input() 여긴아닌거같은데말이지 
        if number % 2 == 0:
            print('even')
        else:
            print('odd')
    
    is_odd(3)

*Q : 만약 내가 입력하는 숫자를 number에 대입하고 싶다면 어디에 input()을 써야하는것인지?*

### 연습문제2

입력으로 들어오는 모든 수의 평균 값을 계산해 주는 함수를 작성해 보자. (단 입력으로 들어오는 수의 개수는 정해져 있지 않다.)

    def avg_numbers(*args): # 입력 개수에 상관없이 사용하기 위해서
        result = 0
        for i in args:
            result += i     # result = result + i
        return result / len(args)
    
    avg_numbers(1,2,3,4,5)

 *args 라는 개념이 생각이 나지 않아 한번에 못풀었다. 

### 연습문제 3

이 프로그램에서 3과 6을 입력했을 때, 9가 나오도록 프로그램을 수정해보자

    input1 = input("첫번째 숫자를 입력하세요:")
    input2 = input("두번째 숫자를 입력하세요:")
    
    total = input1 + input2
    print("두 수의 합은 %s 입니다" % total)

    input1 = input("첫번째 숫자를 입력하세요:")
    input2 = input("두번째 숫자를 입력하세요:")
    
    total = int(input1) + int(input2) #int로 바꿔줘야하는 이유는 input1이 문자열로 들어갔기 때문
    print("두 수의 합은 %s 입니다" % total)

int를 써야한다는 것은 알았으나 입력이 문자열로 들어가기 때문이라는 것을 몰랐다.
| Date | Teacher | Category |
|:----|:----|:----|
|08.09 | Sunmi, Archal | SQL, Python |

<br>

Python
====

테스트 방법론
---
[* 아샬님 수업 설명](https://docs.google.com/document/d/107PJDmhW6bLBE8fAw2mB7wSeK-VnHFoH6m9DaxiVHcI/edit#)

테스트 코드를 먼저 작성을 한 후에 함수를 만들어가야 한다.(주어진 예시들로!)

1. **눈으로 확인**
2. **자동화**
    > **단정문(Assertion)** = Expected Actual <br>
        assert뒤에 참이 오면 에러가 생기지 않는다.

    ``` python
    assert 1 + 1 == 2


    def double(n):
    return n * 2


    assert double(2) == 4
    assert double(1) == 2
    assert double(1234) == 2468


    # print(double(2))
    # print(double(1))
    # print(double(1234))

    ```
3. **테스트**를 단계 단계 _쪼개서_ 하는 것이 좋다.

    RED<br>
    GREEN<br> 
    REFACTORING<br>

    <br>
4. 터미널에서 **pip install pytest** -> or 파이참에서 알아서 설치해줌.
    > 파이참 preferences -> tools -> python integrated tools -> Testing -> pytest 설치
    <h5>pip : 파이썬 라이브러리 관리자



<br><br>    

---
## QUIZ

``` python
# score가 다음과 같은 형태로 주어졌을 때
scores = [80, 100, 70, 90, 40]

# total, average 를 만드려고 합니다.

# 1. 테스트 코드 작성하기
# 2. TDD(Test Driven Development)로 함수 만들기
# 3. 코드를 GitHub 에 올리기
# 4. 코드 리뷰

def test_total():
    assert total([80]) == 80
    assert total([80, 20]) == 100
    assert total([80, 100, 70, 90, 40]) == 80 + 100 + 70 + 90 + 40


def test_average():
    assert average(scores) == 76.0

def total(numbers):
    accumulrator = 0
    for i in range(len(numbers)):
        accumulrator += numbers[i]
    return accumulrator
    # return sum(numbers)


print(total(scores))


def average(numbers):
    return sum(numbers) / len(numbers)


print(average(scores))

```

------

## **오늘 배운 파이썬 명령어**
    assert
    # TODO: 작업해야함
    pass(return과 같지만 아직 작업중이라는 것을 표시하는 것)

## **오늘 배운 점**
    보통 문제에 목표가 나와 있으니, 
    테스트 코드를 먼저 작성을 하고 함수를 만들어가기 시작하는 새로운 방법론을 알게 되었다. 
    -> 알고리즘을 암산으로 계속 하려고 하지말고 테스트를 통해서 함수를 찾아가자.(리쳐드 파인만식...ㅋㅋㅋ)
    -> 프로그래밍적인 방법론이라기 보다 분석에 최적화된 방법론인 것 같아서 새로운 기분!!



# Python 기초 문법

### 문자와 변수

```python

# 출력
print(123)
print('문유나')
print("문유나")

# 연산
print(123+456)
print(100*100)

# 변수
name = "문유나"
print(name)

# 인덱스
name = "가나다라마바사"
print(name[0])
print(name[0:3])
 
```

### 문자와 변수 결과

<figure><img src="../.gitbook/assets/파이썬 테스트.png" alt=""><figcaption></figcaption></figure>

***

### 리스트/딕셔너리

```python

# 리스트 List
students = ['문유나','문세나','문한나','문멍개','문개똥']
subStudents = ['문유나','문세나','문한나',['문멍개','문개똥']]

# 리스트 List 출력, []안에 원하는 자료의 인덱스를 입력
print(students[1])

# 특정 인덱스의 값을 변경
students[2] = 1000
print(students)

# 2차 배열 수정 
subStudents[3][0] = '해삼'
print(subStudents)

# 딕셔너리 Dictionary key:value
members = {'문유나':29 ,'문세나':26,'문한나':20}

# 딕셔너리 Dictionary 출력
print(members['문유나'])

```

### 리스트/딕셔너리 테스트 결과&#x20;

<figure><img src="../.gitbook/assets/파이썬테스트.png" alt=""><figcaption></figcaption></figure>

***

### if 조건문

```python

# 특정 조건에서 코드를 실행시킬 경우
# if 조건식 :
#  실행할 코드

# 단순 부등호
num = 10
if num >= 10:
    print('num은 10 이상입니다.')

# if-in 문법 (대소문자 구분)
list = ['문유나','문세나','문한나']
if '문유나' in list :
    print('문유나 학생이 있습니다')
    
# if-else 문법
num = 4
if num >= 10:
    print('num은 10 이상입니다')
else :
    print('num은 10 이하입니다.')

```

### if 조건문 테스트 결과

<figure><img src="../.gitbook/assets/파이썬 ㄷ.png" alt=""><figcaption></figcaption></figure>

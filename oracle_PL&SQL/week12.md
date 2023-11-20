# PL/SQL
SQL + 절차적 언어의 요소 

Program Languege
변수 -> 선택처리 -> 반복처리 -> 배열 -> 포인터 -> 파일

배열명은 포인터 상수, 포인터끼리 연산이 됨

자연어 --(번역)--기계어
번역 - 어셈블러/컴파일러/인터프리터

c언어의 등장 (functional programing) -> go to 줄임
java의 등장 -> re use (상속), 요구사항에 따른 약간의 수정 (다형성)

## PL 
순차 / 선택 / 반복

순차 : 변수 -> data type
선택 : if / switch
반복 : for / do-while / while + while을 더 많이 씀

```
for(int i=0;(첨자)...)
```

**data**
저장값의 갯수에 따라
- 단일데이터
- 모임데이터
&nbsp;&nbsp;&nbsp;&nbsp;- 동종(배열) : k\[i(첨자)]
&nbsp;&nbsp;&nbsp;&nbsp;- 이종(구조체) +레코드, 스트럭쳐


## PL/SQL의 구성

PL + SQL (DML, TCL) dbms
ORACLE
- DDL (TABLE, VIEW, INDEX, SEQUENCE)
- DML (SELECT -> DQL)
- DCL (TCL(COMMIT(원본반영), ROLLBACK(작업철회)))

구성
EXCUTE

선언부 : 변수, 상수,  커서 등을 선언
실행부 : 선택처리, 반복처리 등 로직
예외처리부 

프로그램의 조금 작은 버전 : 모듈
1. 

@ 앳더자일

## 변수
#### 1. 스칼라 타입 
#### 2. 참조 타입
- %type 
```sql
필드명.[참조할 필드명]%type
```
- %rowtype : 잘 안 씀

> = (equality / assignment)
동등 =, 대입 :=

>DBMS_OUTPUT.PUT_LINE()
한 단어를 출력해주는 함수


## 반복처리문

i j k l m n 정수 , 첨자 -> 포트란에서 먼저 씀

```sql
# for문
for loop
end loop;
```
```sql
# while문
while loop
end loop;
```

### 데이터 값을 저장하는 법 (SELECT)
select 의 결과 -> into

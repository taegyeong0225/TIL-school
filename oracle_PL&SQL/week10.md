P.164~

&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┍ Select (검색) → DQL <br>
DML  ┝ Update (갱신) ┒
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ┝ Insert &nbsp;(삽입)&nbsp;&nbsp;┣→ DML <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; ┕ Delete (삭제)&nbsp; ┚ <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;(오라클에서는 나눠서 표현한다) <br>

## TCL (DCL의 일종)
COMMIT - 트랜잭션 종료
ROLLBACK - 트랜잭션 작업 철회 (트랜잭션)

서로 다른 작업? 트랜잭션 영역의 차이로 다른 창에서는 안보임
abort 비정상적인 종료? 종료 전 트랜잭션이 사라짐
 
원본에 반영하는 방법
- commit
- close
- DDL
 
## 트랜잭션
- 사용자에 의해 실행된 SQL문의 집합
- 변경된 데이터는 TCL에 의해 데이터베이스에 반영됨
- 트랜잭션 처리는 데이터 무결성(integrity) 유지
- DML문의 한 번 이상 실행이 하나의 트랜잭션이 됨
- DML문은 하나의 명령이 하나의 트랜잭션이 됨

> 원본 DB를 copy 한 것

┍ single user system
┕ multi user system┍ multi programming : 1 CPU, many PG <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;┕ multi processing

- Program
- process
실행중인 프로그램
CPU에 서비스를 받고 있는 프로그램
PCB를 받고 있는 프로그램
(메모리에 적재됐다고 무조건 실행됐다고 보기는 어려움)
- processor (CPU와 I/O channer(CPU를 도움, PC에는 없고 server에는 있음))

#### 시분할 시스템 (Time-Sharing 시스템)
Queue → FIFO
A B C A B C

\* 라운드로빈


|cpu 사용시간|1ms|1ms|1ms|1ms|1ms|1ms|
|---|---|---|---|---|---|---|
|프로그램 A|A|||A||
|프로그램 B||B|||B|
|프로그램 C|||C|||C|
time slice은 보통 1ms
CPU이 서비스를 다 해주면 time out! 맨 뒤로 간다
- 기다리는 프로그램은 wait 상태
- CPU의 서비스를 받고 있는 프로그램은 running 상태

![](https://velog.velcdn.com/images/taegyeong0225/post/4ec338e8-3e7a-401a-9cfe-a8b0afa715b2/image.png) 생성 : 실행
준비 : queue에 있는 것, wait
실행 : cpu의 서비스를 받는 상태
wait → running : 디스패치
대기(보류) : CPU의 서비스를 받으려면 PG와 data는 Memory에 있어야 한다. 근데 실제 모든 프로그램은 디스크(virtual memory)에 있다. PG 전체가 메모리에 들어갈 수 없다. → 프로그램을 일정 단위로 쪼갬 (=page)
다음 페이지가 메모리에 올라오지 않으면 cpu가 놀게 된다 → 보류 상태
I/O channer이 다음 페이지를 올리고 CPU에게 보고 (=interrupt) 후 보류(block)에서 준비(ready) 상태로 이동

프로그램 1 ┒
프로그램 2 ┣ [Queue] ─ CPU 
프로그램 3 ┚

|CPU|
|---|
|<center>레지스터</center>|

#### Paging (page in + page out)

하드디스크(virtual memory)에 있는걸 실행시킴
CPU는 디스크에 있는 것들을 직접 실행은 못함
→ 하드디스크를 일정하게 나눔, 그 단위가 페이징

page in : disk → memory (disk에서 memory로 올리는 것)
page out : memory → disk (memory에서 disk로 내리는 것)

CPU가 paging 일을 하기엔 너무 고급 자원? 부하가 많이 걸림
→ CPU의 비서? I/O channer이 해줌

time out 후 메모리에 page가 없을 경우 CPU가 I/O channer가 page in을 지시 (= page fault)

memory가 꽉 찼을 때 뭘 내릴지? → 스케줄링의 한 방법 (쉬운건 FIFO)

![](https://velog.velcdn.com/images/taegyeong0225/post/49d095f6-353e-4052-8bb5-fcd08105916e/image.png)

\* block에서 ready로 못 감

sagmentation: 일정하지 않은 페이지

세그멘테이드 페이지

PMT

#### ⭐⭐⭐ 프로세스 상태 변화 process state transition
![](https://velog.velcdn.com/images/taegyeong0225/post/905c770c-baaf-4adc-9242-f7eb249be964/image.png)
ready(queue) -(dispatch)-> running
page fault 발생시 blocked로 이동

------------
#### 추가 ) * 타임 슬라이싱의 길이의 따른 장단점 

-----------------



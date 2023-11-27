# 유스케이스 다이어그램
## 1. 유스케이스 다이어그램의 구성 요소와 표현
### 유스케이스 다이어그램의 필요성
요구사항정의가 개발 및 설계에서 매우 큰 비중을 차지하기 때문 (who, what, interfce)
![](https://velog.velcdn.com/images/taegyeong0225/post/9474b093-341f-4fcc-b2ad-e367e9ad66f9/image.png)

- 액터 (actor) : 개발할 시스템 외부의 존재, 이벤트 흐름을 시작하게 하는 객체
- 유스케이스 (UseCase) : 시스템 내부에 해당하는 단위 기능, 사용자 관점에서 시스템을 모델링 / 시스템을 수행하는 일련의 행위(과정 X)


## 2. 유스케이스 다이어그램의 관계
\* UC : 유스케이스 
### 유스케이스 사이의 관계
의존 관계
1. 포함 관계 (⇢) : 다른 UC에서 기존 UC를 **재사용**할 수 있음을 나타냄
&nbsp;&nbsp;&nbsp;&nbsp; 하나의 UC를 수행할 때, 같은 기능이 있는 다른 UC가 반드시 수행됨
&nbsp;&nbsp;&nbsp;&nbsp; A ⇢ B 일 때 A를 하면 B가 무조건 수행됨
2. 확장 관계 (⇠) : 기존 UC에서 진행 단계를 추가하여 새로운 UC를 만들어 내는 관계
&nbsp;&nbsp;&nbsp;&nbsp; 확장하는 UC는 상위 UC로부터 어떤 **특정 조건**에 의해 수행
&nbsp;&nbsp;&nbsp;&nbsp; 기본 UC를 수정하지 않고 새로운 요구 사항 추가로 표현하고자할 때 
>  확장 관계 != 포함 관계
![](https://velog.velcdn.com/images/taegyeong0225/post/1670c1a6-20c2-447d-b1b7-c5efcf8438fe/image.png)

### 액터 사이의 관계
1. 일반화 관계
추상적인 액터 - 구체적인 액터
![](https://velog.velcdn.com/images/taegyeong0225/post/b59d800b-d6b8-4411-926a-f95acec4c371/image.png) ![](https://velog.velcdn.com/images/taegyeong0225/post/d3065b3c-43da-4126-b3ed-4504dbb138dc/image.png) ![](https://velog.velcdn.com/images/taegyeong0225/post/325cc9f6-6355-4182-8381-68ae5c395000/image.png)

2. 중복 관계
유스케이스 모델링은 유스케이스 이벤트 흐름에서 중복된 부분이 있을 때 설정
![](https://velog.velcdn.com/images/taegyeong0225/post/6d6af63f-80e5-4f80-98e4-646d62ef5f9f/image.png) ![](https://velog.velcdn.com/images/taegyeong0225/post/7158c73b-6829-4c11-bae3-a4f6febbb4dd/image.png)

### 액터와 유스케이스 사이의 관계
- 연관 관계 (-) : 정보를 주고 받는 액터와 유스케이스 표시
![](https://velog.velcdn.com/images/taegyeong0225/post/4a0ac6fe-350a-42af-b0b2-d4ff841d692e/image.png)


## 3. 유스케이스 다이어그램의 단계별 모델링 : 깨비책방 관리 시스템
1. 시스템 상활 분석
2. 액터 식별
3. 유스케이스 식별
4. 유스케이스 다이어그램 작성
5. 유스케이스 명세서 작성
6. 유스케이스 실체화 직성 (순차(이벤트 흐름)/활동(화면 흐름))
![](https://velog.velcdn.com/images/taegyeong0225/post/2c7b683c-2c1f-42b7-8361-8f93cf8f4735/image.png)

## 4. 유스케이스 다이어그램 모델링 연습

 -- 끝

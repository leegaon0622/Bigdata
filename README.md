# 도시녹지환경 빅데이터 요약분석

<br/><br/>
## 01. 프로젝트 개요

도시 공원이란? 
- 도시 자연 경관의 보호와 시민의 건강, 휴양 및 정서생활의 향상에 기여함을 목적으로 조성, 관리하는 공원

<br/><br/>
## 02. 프로젝트 설계

- 사용 언어: Python
- 개발 환경: Google Colaboratory(https://colab.research.google.com )
- 데이터 수집 방법: 공공데이터 포털(https://www.data.go.kr)
- 사용하는 데이터: 전국 도시 공원 정보 표준 데이터
  <img width="700" height="" src="./image/dataset.png"/>

<br/><br/><br/>
## 03. 프로젝트 분석

### 03-1. 한글 폰트 설정

> ### 1) 폰트 설치하기
> <img width="" height="" src="./image/03-1-1.png"/>  <br/><br/>
>
> ### 2) 런타임 재시작 
> <img width="" height="" src="./image/03-1-2.png"/>  <br/><br/>
>
> ### 3) 한글 폰트 설정 및 마이너스 표시 문제 해결 
> <img width="" height="" src="./image/03-1-3.png"/>  <br/><br/>


### 03-2. 데이터 전처리

> ### 1) info() 함수 이용한 정보 확인
> <img width="" height="" src="./image/03-2-1.png"/><br/>
> - 단순 공원명 뿐만 아니라 공원의 종류를 세분화하며 도로면과 지번 주소 모두 표기하는 것을 확인할 수 있다.
> - 공원의 면적과 공원이 보유하고 있는 시설이 무엇인지 (운동, 유희, 편익, 교양, 기타)를 알 수 있다.
> - 관리하는 기관명과 전화번호를 통해 추후 문의사항 등과 관련하여 연락할 수 있다.
>
> ### 2) count() 함수 이용한 데이터 개수 확인
> <img width="" height="" src="./image/03-2-2.png"/><br/>
> - 관리번호, 공원명, 공원구분의 데이터 개수를 통해 현재 우리나라의 도시공원이 총 18,210개 있음을 알 수 있다.
> - 현재 우리나라 도시공원은 4,951곳의 운동시설, 6,517곳의 유희시설, 5,255곳의 편익시설, 
    847곳의 교양시설, 2720곳의 기타 시설을 보유하고 있으며 유희시설을 가장 많이 보유하고 있음을 알 수 있다.
>
> ### 3) 통계함수(mean(),max(),min()) 이용한 공원 면적 확인
> <img width="" height="" src="./image/03-2-3.png"/><br/>
> - 우리나라 공원 면적의 평균은 대략 32,703㎡이며가장 큰 공원의 면적은 대략 9,320,660㎡이다.
> - 또한 가장 작은 공원의 면적은 대략 1㎡이다
>
> ### 4) 공원 면적 결측치 확인
> <img width="" height="" src="./image/03-2-4.png"/><br/>
> - 공원 면적의 NaN 값은 21개이다.
> - 이는 현재 공사중인 도시공원이 21곳이라는 의미이다.
>
> ### 5) 도로명/지번 주소 결측치 확인
> <img width="" height="" src="./image/03-2-5-1.png"/><br/>
> - 도로명 주소의 결측치는 13,248이고 지번 주소의 결측치는 344이다.
> - 우리나라 공원 18,210개 중 도로명 주소와 지번 주소를 모두 알 수 있는 공원은 총 4,618개이며 전체의 약 1/4정도다.
>
> ### 6) drop_duplicates() 이용한 공원구분 중복 데이터 처리
> <img width="" height="" src="./image/03-2-6-1.png"/> <img width="300" height="380" src="./image/03-2-6-2.png"/><br/>
> - 현재 우리나라는 공원을 위와 같이 구분한다. 
> - 데이터 값을 통해 공공데이터 포털은 마을마당, 도시 농업공원 등 조금 더 세분화하여 공원을 구분하였음을 할 수 있다.
>
> ### 7) 각 지역 별 공원 수
> **split() 함수 이용한 소재지도로명주소를 '시'별로 나누기**<br/>
> <img width="" height="" src="./image/03-2-7-2.png"/><br/>
> - 데이터 값을 통해 영월군, 대전, 서울과 같이 데이터가 정확하게 나누어지지 않았음을 확인 할 수 있다.
> **replace() 함수 이용한 같은 지역으로 묶기**<br/>
> <img width="" height="" src="./image/03-2-7-4.png"/><br/>
> - 데이터 값을 통해 각 지역별 공원 분포도를 알 수 있으며 경기도가 1,467개로 가장 많고, 제주도가 17개로 가장 적음을 알 수 있다.
>
> <br/><br/><br/>

### 03-3. 전국 공원 분포도 시각화

> ### 1) 위도, 경도를 이용하여 전국 공원 분포도 시각화하기




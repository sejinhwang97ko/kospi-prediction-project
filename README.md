# VAR, VARMAX, LSTM 모델을 이용한 “코스피 200 경기소비재지수” 예측
## 프로젝트 기간: 약 1달(270시간)
### 데이터 크기: 184개의 instances, 23개의 columns
* 주제를 선정하게 된 이유:
  - (문제)부티크 사기 등 불공정거래 늘어나고 있음. 예방할 수 있는 모델 필요
  - KOSPI종가와 경기종합지수의 선행지수순환변동치 거의 같은 추세. BUT 시차 보이는 곳 존재
  - KOSPI종가는 광범위 함 ⇒ KOSPI200 선정
  - 거시적 경제 지표와 시계열 데이터를 활용해 경기에 민감한 종목을 모아둔 “경기 소비재 지수”를 예측해보자. 
* 거시 경제는 중기. 일별 데이터와는 맞지 않음 ∴ 월별 데이터
  - ⇒예측: 2020.05~2023.04 (: 36개월> 30) / 학습은 148개
* 거시 경제 지표: 선행, 동행, 후행
  -  예측 모델을 만들고 민감한 정도를 보여주는 “경기 소비재 지수”를 예측할 거기 때문에 선행 위주, 경기 종합지수 선행지수순환변동치 참고

|정보|내용|
|---|---|
|데이터 출처|Investing.com, FinanceDataReader, 트레이딩뷰, KRX, OECD, ECOS, KOSIS, FRED, 네이버증권|
|학습 모델|VAR(벡터자기회귀모형. Vector Autoregression), VARMAX(Vector Autoregression Moving-Average with Exogenous Regressor), LSTM|
|변수 선택 방법|Granger Causality 인과성 검정|

* 결과/평가 (벤치마크 누적수익률 159%)
  1. VAR 230%
  2. VARMAX 236%
  3. LSTM+CNN 183%

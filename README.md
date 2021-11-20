# EDA-Analytics-baseball
> Colab nootbook : https://colab.research.google.com/github/Hyun-Jun-Lee/EDA-Analytics-MLBHitter/blob/main/EDA%26Analytics_MLBhitter.ipynb <br>
> nbi views : https://nbviewer.org/github/Hyun-Jun-Lee/EDA-Analytics-MLBHitter/blob/main/EDA%26Analytics_MLBhitter.ipynb

## 목차

- [EDA-Analytics-baseball](#eda-analytics-baseball)
  - [목차](#목차)
    - [Dataset](#dataset)
    - [Preprocessing](#preprocessing)
    - [EDA & Analytics](#eda--analytics)
      - [Trend Change Per Season](#trend-change-per-season)
      - [Who is The Strongest Hitter in 00s?](#who-is-the-strongest-hitter-in-00s)
      - [Who is The Strongest Hitter in 10s?](#who-is-the-strongest-hitter-in-10s)
      - [Albert Pujols vs Mike Trout](#albert-pujols-vs-mike-trout)
    - [ToDoList](#todolist)



***

***

[위로가기](#목차)


### Dataset

<a href="http://www.seanlahman.com/baseball-archive/statistics/">Sean Lahman's website</a>

- colab Free 버전 RAM 용량으로 처리하기에는 Dataset 크기가 너무 커서 데이터 정리

![image](https://user-images.githubusercontent.com/76996686/142727142-1fdaf70f-2c71-4c64-8d1a-0db80408e0b2.png)

<br>

### Preprocessing

- NA values check
  - NA 비율 10% 이상 Feature -> 'mean' 값으로 대체
  - NA 비율 10% 이하 Feature -> '0' 으로 대체

<br>

- 2020년은 코로나로 인한 단축 시즌으로 제외
- 현대적인 야구 규칙이 제정된 1902년 이후 데이터만 선정

<br>

![image](https://user-images.githubusercontent.com/76996686/142727619-48456211-d604-4049-95dd-2f3c3cbbf1c9.png)

- Outlier
  - 현재 경기 수 `162` 경기
  - 역대 한 시즌 최다 득점 `198`
  - 역대 한 시즌 최다 안타 `262`

<br>

### EDA & Analytics

#### Trend Change Per Season

> `HR` - `SB` - `SH`

![image](https://user-images.githubusercontent.com/76996686/142727866-f858dc40-976c-404f-905e-1163a7263bd7.png)

- 세이버 메트릭스를 통해 득점에 가장 효과적인 기록이 무었인지에 대한 연구가 계속 되었고, statcast 기술의 도입으로 타구 속도, 발사 각도 등을 분석할 수 있게되면서 장타의 중요성 증가 -> 홈런의 수가 급격히 증가중
- 그에 비해 도루, 희생번트는 기대득점이 낮고, 특히 도루는 부상위험이 크기 때문에 시도 및 성공횟수가 줄어드는 추세
    - 세이버메트릭스에 따르면 무사 1,2루 상황에서의 희생 번트만 가치가 있음

<br>

> `ISO` - `k%` - `BB/K`

![image](https://user-images.githubusercontent.com/76996686/142727956-573e2786-fa7a-4750-bc93-1513f58e06a7.png)

- ISO : 장타율 - 타율, 절대적인 타자의 파워를 나타내는 지수
- K% : 타석당 삼진 비율
- BB/K : 삼진 한개 당 볼넷의 수, 타자의 선구안을 판단하는 지표

<br>

ISO 그래프를 통해 타자들이 공을 멀리보내기 위해 강하게 타격하려고 하는 것을 알수 있음<br>
K%, BB/K를 통해 강하게 타격함에따라 스윙이 커져서 타석당 삼진 비율 증가하고 볼넷 비율이 줄어듬을 알 수 있음

<br>

#### Who is The Strongest Hitter in 00s?

- Top 5 Homerun Leader in 00s

![image](https://user-images.githubusercontent.com/76996686/142729687-da37048f-8f46-4c9b-b296-f3f73049995a.png)

<br>

- Top 5 HR Leader Detail Stat

![image](https://user-images.githubusercontent.com/76996686/142729715-e437d6de-7366-4a29-819a-6726e82236c0.png)

<br>

- My choice is Albert Pujols
  - 선정이유
    1. 총 홈런 개수는 4등이지만,ISO(순수장타율)는 `0.288`로 1등
    2. K% : `9.3%` & BB/K : `1.3` -> 다른 타자와 비교해 압도적인 수치, 파워와 함께 선구안도 갖추었다고 볼수 있음
    3. 타/출/장/OPS = `0.332/0.422/0.620/1.042` -> 역사상 최고의 10년이라고 뽑을 수 있을만한 아름다운 기본 Stat
  - 수상기록<br>
  ![image](https://user-images.githubusercontent.com/76996686/142729981-8180cb3c-52a3-4bae-9b4e-4e303dd924e1.png)

<br>

#### Who is The Strongest Hitter in 10s?

- Top 5 Homerun Leader in 10s

![image](https://user-images.githubusercontent.com/76996686/142730155-16da5e9d-bfe2-43dd-b10d-7f4282e5878d.png)

<br>

- Top 5 HR Leader Detail Stat

![image](https://user-images.githubusercontent.com/76996686/142730162-d92a3df1-319b-4d7d-bf32-d0ab566d3194.png)

<br>

- My choice is Mike Trout
  - 선정이유
    1. 총 홈런 개수는 5등이지만,ISO(순수장타율)는 `0.268`로 1등
    2. OBP : `0.421` -> 데이터 야구 시대에서 중요시 여겨지고 평균적으로 가장 기복이 없다고 여겨지는 Stat
    3. BB : `863` -> 타 선수 대비 압도적 기록, 타격에 기복이 있을시에도 꾸준히 활약해 줄 수 있는 부분 
    4. 3B : `65` -> 장타력 뿐만 아니라, 스피드 까지 갖추었음
  - 수상기록<br>
  ![image](https://user-images.githubusercontent.com/76996686/142730193-af350c7b-fbdc-479b-8640-68a3700adfd0.png)

<br>

#### Albert Pujols vs Mike Trout

- Comparison by age

  1. vs OPS+
  ![image](https://user-images.githubusercontent.com/76996686/142730280-5f585107-1d6a-4f61-96c3-92f800b7a65c.png)
  * OPS+ : 리그 수준 차이, 다른 시기 활동한 타자들을 비교하기 위해 만들어진 리그 평균 대비 OPS 지표(OPS+=150 -> 해당 시즌 리그 평균 대비 1.5배 우수한 OPS)

  2. vs HR
  ![image](https://user-images.githubusercontent.com/76996686/142730358-1c137e88-ae4d-45cf-8344-ccacda58a08d.png)

  3. vs ISO
  ![image](https://user-images.githubusercontent.com/76996686/142730381-d3df71a5-c7ea-482a-842e-46925c2ce8ac.png)

<br>

- Comparison by Accumulated stat

![image](https://user-images.githubusercontent.com/76996686/142730427-81ab7037-d1c7-4903-b6f4-a7756f49140b.png)

<br>

### ToDoList

- [ ] 2020,2021 데이터 수집
- [ ] WAR, WRC, WPA 등 다양한 기록 데이터 수집(by Crawling)
- [ ] Time Series Forecasting(ARIMA, LSTM)
- [ ] 예측 및 EDA 검색하는 WEB 구현 해보기
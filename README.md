# Comparing Scan Statistics for Zero-inflated Spatial Count Data: A Case Study of Arson data
### 2023 한국자료분석학회 동계 학술논문발표대회 포스터 발표 (24.01.26)
***
## Abstract
　In the analysis of count data such as crime and disease incidence, the excess of zero counts are commonly observed so that the conventional Poisson model has a limit to explain the data.  To identify significant areas of event occurrence, we consider the Scan-Poisson statistic, based on the Poisson model, and the Scan-ZIP (Zero-Inflated Poisson) statistic, which accounts for zero inflation.  By conducting the simulation studies, we compare the results of both approaches. We demonstrate that the Scan-ZIP statistic is more effective in identifying clusters in zero-inflated spatial data. Also, the results show that Scan-Poisson statistic steadily deteriorates as the number of zeros increases, producing biased inferences.  To illustrate the usage, we applied these methods to arson incident data from 426 administrative districts in Seoul (2012-2021) to detect significant areas of arson risk. <br>
<br>
*Keywords: spatial scan statistics, zero-inflation, multiple cluster detection, arson data, Seoul*

## Methodology
### Scan-Poisson statistic
![image](https://github.com/white-bean/Scan-statistics/assets/58061467/7a0e50a4-be71-42df-a55f-211872a68191)

### Scan-ZIP statistic
![image](https://github.com/white-bean/Scan-statistics/assets/58061467/9722b486-c981-4b13-bb9c-0331e41add32)
- 단, 해당 위치의 데이터가 structural zero인지 모를 경우에는, EM 알고리즘을 이용해 $\delta$ 를 추정한다.

## Simulation
### Settings
![image](https://github.com/white-bean/Scan-statistics/assets/58061467/50d086be-377d-4d62-8361-4a7435408e76)
- 203개의 hexagonal cell들로 이루어져 있으며 인접한 cell들 간의 거리는 같음
- 어둡게 칠한 부분은 true cluster이며 x 표시가 된 부분은 structural zero 지역을 의미함

### Result
![image](https://github.com/white-bean/Scan-statistics/assets/58061467/8829be62-352c-4c3e-9d3c-dc8ad988cb13)

## Application
- 사용 데이터 : 서울특별시 원인별 화재발생(동별) 데이터 중 방화 카테고리에 해당하는 데이터 (2012-2021)
![image](https://github.com/white-bean/Scan-statistics/assets/58061467/597a46b9-b8d2-40c2-96c7-b64782de2cc8)
- left : 방화 건수
- right : 인구 10만 명 당 방화 발생률

### Result
![image](https://github.com/white-bean/Scan-statistics/assets/58061467/e61e7718-49e0-4e59-9341-1a408b42ee19)
- left : Scan-Poisson으로 진행한 cluster 결과
- right : Scan-ZIP(EM)으로 진행한 cluster 결과

![image](https://github.com/white-bean/Scan-statistics/assets/58061467/3cf90f6c-5e9d-4875-8ccb-dd34d7bfa1da)

***
**References**<br>
Andre L. F. Cancade. Et al. A spatial scan statistic for zero-inflated Poisson process, 2018.<br>
M. Kulldorff, T. Tango, and P. Park. Power comparisons for disease clustering tests. Computational Statistics & Data Analysis, 42:665–684, 2003. <br>
서울특별시,「서울특별시기본통계」, 2021, 2023.12.06, 원인별 화재발생(동별)<br>
서울특별시,「주민등록인구(동별)」, 2022, 2023.12.08, 서울시 주민등록인구 (동별)<br>
GEOSERVICE-WEB)[Website]. (2023.12.20). URL: http://www.gisdeveloper.co.kr/?p=2332

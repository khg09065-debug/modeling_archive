# 군집화 모델별로 어떻게 상권이 묶이며 프리미엄 순위가 어떻게 되는가?

- **subway_archive의 고도화 레포지토리**로써 subway_archive가 전철역 하나하나씩의 상권의 성격을 평가하는 앱이라면 **modeling_archive에서는 군집화 모델별로 상권이 어떻게 묶이는지**를 파악하는 레포지토리

## 🛠️ 기술 스택 및 개발 환경

- **Languege**: `Python 3.13`
- **Library**: `pandas`, `numpy`, `sklearn`, `pyplot`, `SQLalchemy`
  - **sklearn**: `sklearn.cluster`, `sklearn.preprocessing`, `sklearn.metrics`
  - **sklearn.cluster**: `KMeans`, `DBSCAN`, `HDBSCAN`, `OPTICS`
  - **sklearn.preprocessing**: `StandardScaler`
  - **sklearn.metrics**: `silhouette_score`
- **Database**: `Mysql`
- **IDE**: `Jupyter Notebook`

| 라이브러리 | 용도 | 비고 |
| :--- | :--- | :--- |
| **Pandas** | 파일 불러오기 | coffee_store, subway DB불러오기 |
| **numpy** | 수식 계산 | 자연로그(1+x) -> 전철역 주변에 카페가 하나도 없음을 방지 |
| **sklearn** | 군집화 모델 | KMeans -> 상권 성격타입 나눔, 
                              DBSCAN, HDBSCAN, OPTICS -> 전철역 상권 묶|
| **pyplot** | 시각화 | |
| **SQLalchemy** | MySQL 연동 | |

## 📂 프로젝트 폴더 구조

```
├── csv/           # 군집 모델별로 상권이 어떻게 묶이는가?
│   ├── 
│
├── model/         # 군집 모델별로 정확도에 대한 결과 확인
│   ├──
│
├── seoul(DBSCAN)/           # 프리미엄, 가성비, (프리미엄+가성비) -> DBSCAN 모델을 사용해 군집화
├── seoul(HDBSCAN)/           # 프리미엄, 가성비, (프리미엄+가성비) -> HDBSCAN 모델을 사용해 군집화
├── seoul(OPTICS)/           # 프리미엄, 가성비, (프리미엄+가성비) -> OPTICS 모델을 사용해 군집화
├── seoul.csv(DBSCAN)/           # 프리미엄, 가성비, (프리미엄+가성비) -> DBSCAN 모델의 군집화 결과
├── seoul.csv(HDBSCAN)/           # 프리미엄, 가성비, (프리미엄+가성비) -> HDBSCAN 모델을 군집화 결과
├── seoul.csv(OPTICS)/           # 프리미엄, 가성비, (프리미엄+가성비) -> OPTICS 모델을 군집화 결과
```

# 재활용 품목 분류를 위한 재활용 교육 도우미 애플리케이션 Re-Upcycle

### 😎Members
| 이제이 | 한수진 | 남은수 |
| --- | --- | --- | 
| 팀장<br>모델링 | 팀원<br>데이터 수집 | 팀원<br>프론트 |
---

### 🔍문제 정의 & Project Overview

- 초등학생들은 **재활용성에 대한 인식 부족**이 부족하며 올바른 쓰레기 분류 방법에 대한 명확한 지식을 갖고 있지 않는다.
- **페트병의 분리수거함** 고르기 설문조사 결과 플라스틱류 수거함을 고른 경우는 187명으로 전체의 68%였고, 페트병을 캔류에 넣어야 한다고 응답한 학생이 **27%** 였다. 금속캔과 페트병의 공통적인 성질인 잘 구겨진다, 잘 찌그러진다 등의 선택을 이유로 들었다. 이는 **구성물질 성질에 대한 이해가 부족**하고, 용어를 잘 알지 못하거나 혹은 **재질을 잘못 이해**하고 있다는 것으로 해석 가능하다.
- 분리수거의 어려움에 대해 초등학생들의 응답 분석결과를 보면 구성물질에 대한 고민이 가장 많았으며, **어떤 것이 플라스틱이고 어떤 것이 비닐류인지** 헷갈린다, 페트병이 플라스틱인지 애매하다. 스펀지는 플라스틱 같기도 하고 스티로폼 같기도 하다. 등의 응답을 찾아볼 수 있었다.
- 실제로 초등학교 3학년 과학교과서에는 물질의 성질이라는 단원이 있는데 여기서 물질의 분류 활동을 처음으로 제시하고 있다. 제시하는 물체를 좀 더 다양화해 학생들이 **재미있게 쓰레기 분리수거를 해보고 업사이클링 방법도 알아볼 수 있는 앱을 사용해보면 흥미를 유발할 수 있을 것이라고 생각된다.**

<br /> ![Image](https://github.com/user-attachments/assets/5e602f38-c624-42af-b53b-df3b2779e40d)
<div align="center">
  
**[초등학생 재활용성 인식 및 쓰레기 분류방법 관련 설문조사]**
</div>

---
### 📊Dataset
- AI허브에서 2만장의 재활용 쓰레기 데이터 수집
- JSON형식의 데이터를 TXT형식으로 변환, 총 8개의 클래스로 라벨링
- 8 class :  Paper, glass, pack, pet, plastic, can, vinyl, battery,styro
이미지 크기 : (1024, 1024)
  
```python
def class_choose(cls):
    paper = ['c_1','c_2_01','c_2_02', 'c_1_01', 'c_2_02_01']
    glass = ['c_4_01_02','c_4_02_01_02','c_4_02_02_02','c_4_02_03_02','c_4_03', 'c_4_03_01', 'c_4_01_01', 'c_4_02_01_01', 'c_4_02_02_01', 'c_4_02_03_01']
    pet = ['c_5_02', 'c_5_01_01', 'c_5_02_01', 'c_5_01']
    plastic =['c_6', 'c_6_01']
    can = ['c_3', 'c_3_01']
    vinyl =['c_7', 'c_7_01']
    battery =['c_9']
    styro=['c_8_01','c_8_02', 'c_8_01_01']

    if cls in paper:
        return 0
    elif cls in glass:
        return 1
    elif cls in pet:
        return 2
    elif cls in plastic:
        return 3
    elif cls in can:
        return 4
    elif cls in vinyl:
        return 5
    elif cls in battery:
        return 6
    elif cls in styro:
        return 7
```
### Models
- Yolov7
---
### 🛠Development diagram
![Image](https://github.com/user-attachments/assets/2f3ed7b2-174e-4bd6-94f3-0b46ab627de7)

---
### 🔥Project plan
![Image](https://github.com/user-attachments/assets/a31f6e39-7da5-45a8-aa20-b8cc1b12aba2)

---
### 💡Result
<p align="center">  <img src="https://github.com/user-attachments/assets/259f7b71-706b-4bde-b943-ac34c4461e54" align="center" width="32%">  <img src="https://github.com/user-attachments/assets/0e013828-52c4-4b98-a976-0bc9d8809d2a" align="center" width="32%">  <img src="https://github.com/user-attachments/assets/8cc97f5c-e992-4141-9434-152d1602b2c0" align="center" width="32%">  <figcaption align="center"></figcaption></p>
<p align="center">  <img src="https://github.com/user-attachments/assets/1135ba67-66a5-4755-aaec-dc8ec91dfe0c" align="center" width="32%">  <img src="https://github.com/user-attachments/assets/a801b349-fa25-4e79-bf84-63ebff666443" align="center" width="32%">  <img src="https://github.com/user-attachments/assets/4b5155e3-719f-483f-ab71-985103cc2769" align="center" width="32%">  <figcaption align="center"></figcaption></p>

![Image](https://github.com/user-attachments/assets/e58fbc03-b8c6-47ca-a765-d53cc9d1f98b)
- 이미지를 업로드하면 분석 결과를 바탕으로 분류 결과와 해당 재활용 쓰레기의 업사이클 유튜브 영상을 추천해준다.
---
### 💡Confusion Matrics & Training rate
<p align="center"> <img src="https://github.com/user-attachments/assets/bdc81361-6b8e-4972-a3bd-e04ad6cebf08"  width="550" height="400"/></p>

- 다음과 같은 **혼동행렬**에서 모델의 정확도를 확인할 수 있다. 유리는 88%,  배터리는 95%, 스티로폼은 96퍼센트로 정확도가 높은 반면 배터리는 오분류된 비율이 18%, 비닐의 정확도는 0.69으로 비교적 낮은 것을 알 수 있다.

<div align="center">
  
![Image](https://github.com/user-attachments/assets/c99a771e-cebc-420b-b3e1-513bf3502771)

</div>

- 객체 탐지 모델의 학습 과정에서의 다양한 메트릭의 변화를 볼 수 있다. 먼저 상단의 그래프를 보면, **Box Loss**는 초기 0.024에서 시작하여 지속적으로 감소한다. 20에코프 이후 안정적인 감소세를 보이고 있으며, 최종적으로 0.014 수준까지 감소하였다. 이를 통해 학습이 안정적으로 진행됨을 확인할 수 있다.
- **Objectness Loss**는 초기 급격한 상승 후 점진적 감소를 보인다. 0.007에서 시작하여 0.0045까지 감소하였다. 이는 모델이 객체의 존재 여부를 잘 학습함을 알 수 있다.
- **Classification Loss**는 초기 0.016에서 시작하여 꾸준히 감소하여 최종적으로는 0.006까지 감소하였다. 이는 클래스 분류 능력이 지속적으로 향상됨을 알 수 있다.
- **Precision**과 **Recall**은 0.65에서 0.85까지 상승하는 것을 통해 두 메트릭 모두 안정적인 성능 향상을 보임을 확인하였다. 다음으로 하단의 그래프를 보면, **val Box**는 학습 세트보다 높은 초기값으로 비교적 빠르게 감소하여 0.025에서 안정화를 이루었고 과적합 징후는 보이지 않고 있다.
- **Val Objectness**는 0.012에서 시작하여 점진적으로 상승하고 있고, 최종적으로는 0.016까지 증가하였다.
- **Val Classification**에서는 초기 급상승 후 점진적 감소를 보이고 있고, 0.018 수준에서 안정화되었다. 이는 일관된 학습패턴을 보여준다.
-**mAP** 성능은 0.75에서 0.90까지 꾸준히 상승하어 모든 loU 임계값이 성능에서 향상되었다. 정리하면, 모든 손실 함수가 안정적으로 감소하였고, 검증 세트에서도 일관된 성능 향상을 보이고 있다. mAP 지표 역시 꾸준히 상승하고 있다.
---
### 💡F1·Precision·Recall vs. Confidence 관계
<div style="text-align:center;">
  <img src="https://github.com/user-attachments/assets/e6cf9dbb-9a06-4bb0-9fdf-fae3b8632551"
       style="display:inline-block; vertical-align:middle; width:45%; margin:0 .5rem;">
  <img src="https://github.com/user-attachments/assets/7e49ccb4-624e-4708-9570-a810cd2b3c09"
       style="display:inline-block; vertical-align:middle; width:45%; margin:0 .5rem;">
</div>
<div style="text-align:center;">
  <img src="https://github.com/user-attachments/assets/08be66d7-edf6-46c1-94d8-5223855f7086"
       style="display:inline-block; vertical-align:middle; width:45%; margin:0 .5rem;">
  <img src="https://github.com/user-attachments/assets/31c572a9-568e-4102-84bb-c5f12482be56"
       style="display:inline-block; vertical-align:middle; width:45%; margin:0 .5rem;">
</div>

- **F1 점수**와 **Confidence**의 관계를 보여준다. 모든 클래스의 F1 평균 점수가 0.86으로 양호한 성능을 보인다. 대부분의 클래스가 confidence 0.2~0.8 구간에서 안정적인 성능을 유지한다. 두번째 사진에서 Precision 곡선을 통해 모델이 클래스별로 얼마나 정확한 예측을 하는지 확인할 수 있었다. X축은 Confidence값, Y축은 Precision값이다.
- **Confidencen**값이 0.986 이상에서 Precision이 1.0에 도달하기에 모델이 전체적으로 높은 성능을 보이고 있음을 알 수 있다. Battery, styro, can 클래서에는 높은 정밀도를 가지고 있지만 plastic, vinyl 클래스는 상대적으로 낮다는 것을 확인한다.
- **Recall-Confidence 곡선은** 재활용 품목 분류 모델의 성능을 더 세부적으로 보여주고 있다. 전체 클래스의 mA@0.5가 0.899로 매우 우수한 성능을 보여준다. 최상위 성능 그룹은 0.980인 스티로폼, 0.977인 배터리이다. 그 다음으로 0.933인 캔, 0.927인 페트가 성능이 높다. 낮은 성능으로는 0.830인 종이, 09793인 비닐이다. 이들은 상대적으로 변형이 쉽고 다양한 형태를 가질 수 있는 물체들이다. 곡선을 살펴보면 초기 구간은 대부분의 클래스가 높지만 후반부분으로 갈수록 어려운 케이스들에 대한 정확도가 저하된다.
- 즉, 전체 모델 성능은 Confidence가 낮을 때 매우 높은 Recall을 달성하지만, Confidence 임계값이 높아질수록 Recall이 급격히 떨어진다. 따라서 하위 성능 클래스인 비닐과 종이의 데이터 품질을 개선할 필요가 있다.

### application flow chart
![Image](https://github.com/user-attachments/assets/8527f4ac-4679-4b18-b920-685cccc8ec86)
### poster
![Image](https://github.com/user-attachments/assets/7f38c10d-09e7-4a96-a8b1-c9585a54be69)




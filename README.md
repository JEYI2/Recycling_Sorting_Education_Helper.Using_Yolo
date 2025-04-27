### 😎 Members
| 이제이 | 한수진 | 남은수 |
| --- | --- | --- | 
| 팀장<br>모델링 | 팀원<br>데이터 수집 | 팀원<br>프론트 |
---

### 🔍 문제 정의 & Project Overview

- 초등학생들은 **재활용성에 대한 인식 부족**이 부족하며 올바른 쓰레기 분류 방법에 대한 명확한 지식을 갖고 있지 않는다.
- **페트병의 분리수거함** 고르기 설문조사 결과 플라스틱류 수거함을 고른 경우는 187명으로 전체의 68%였고, 페트병을 캔류에 넣어야 한다고 응답한 학생이 **27%** 였다. 금속캔과 페트병의 공통적인 성질인 잘 구겨진다, 잘 찌그러진다 등의 선택을 이유로 들었다. 이는 **구성물질 성질에 대한 이해가 부족**하고, 용어를 잘 알지 못하거나 혹은 **재질을 잘못 이해**하고 있다는 것으로 해석 가능하다.
- 분리수거의 어려움에 대해 초등학생들의 응답 분석결과를 보면 구성물질에 대한 고민이 가장 많았으며, **어떤 것이 플라스틱이고 어떤 것이 비닐류인지** 헷갈린다, 페트병이 플라스틱인지 애매하다. 스펀지는 플라스틱 같기도 하고 스티로폼 같기도 하다. 등의 응답을 찾아볼 수 있었다.
- 실제로 초등학교 3학년 과학교과서에는 물질의 성질이라는 단원이 있는데 여기서 물질의 분류 활동을 처음으로 제시하고 있다. 제시하는 물체를 좀 더 다양화해 학생들이 **재미있게 쓰레기 분리수거를 해보고 업사이클링 방법도 알아볼 수 있는 앱을 사용해보면 흥미를 유발할 수 있을 것이라고 생각된다.**

<br /> ![Image](https://github.com/user-attachments/assets/5e602f38-c624-42af-b53b-df3b2779e40d)
<div align="center">
  
**[초등학생 재활용성 인식 및 쓰레기 분류방법 관련 설문조사]**
</div>

### 📊Dataset
- AI허브에서 2만장의 재활용 쓰레기 데이터 수집
- JSON형식의 데이터를 TXT형식으로 변환, 총 8개의 클래스로 라벨링
  
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
---
### 💡Result
<p align="center">  <img src="https://github.com/user-attachments/assets/259f7b71-706b-4bde-b943-ac34c4461e54" align="center" width="32%">  <img src="https://github.com/user-attachments/assets/0e013828-52c4-4b98-a976-0bc9d8809d2a" align="center" width="32%">  <img src="https://github.com/user-attachments/assets/8cc97f5c-e992-4141-9434-152d1602b2c0" align="center" width="32%">  <figcaption align="center"></figcaption></p>
<p align="center">  <img src="https://github.com/user-attachments/assets/1135ba67-66a5-4755-aaec-dc8ec91dfe0c" align="center" width="32%">  <img src="https://github.com/user-attachments/assets/a801b349-fa25-4e79-bf84-63ebff666443" align="center" width="32%">  <img src="https://github.com/user-attachments/assets/4b5155e3-719f-483f-ab71-985103cc2769" align="center" width="32%">  <figcaption align="center"></figcaption></p>

### 💡Confusion Matrics
<p align="center"> <img src="https://github.com/user-attachments/assets/1f608883-2974-4e86-93e1-04316962e372"  width="500" height="400"/></p>
- 다음과 같은 혼동행렬에서 모델의 정확도를 확인할 수 있다. 유리는 88%,  배터리는 95%, 스티로폼은 96퍼센트로 정확도가 높은 반면 배터리는 오분류된 비율이 18%, 비닐의 정확도는 0.69으로 비교적 낮은 것을 알 수 있다.
  
![Image](https://github.com/user-attachments/assets/7f38c10d-09e7-4a96-a8b1-c9585a54be69)
![Image](https://github.com/user-attachments/assets/2f3ed7b2-174e-4bd6-94f3-0b46ab627de7)

### Models
- Yolov8

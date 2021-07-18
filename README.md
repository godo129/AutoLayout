# **Swift Auto Layout**
 ---
 
### 목차
- [Auto Layout이 나온 배경](#1._Auto_Layout이_나온_배경)
- [Auto Layout 구성](#2._Auto Layout 구성)
- [제약 세부 정보](#3._제약 세부 정보)

## 1._Auto Layout이 나온 배경 

스위프트 Auto Layout은 기존의 Frame-Based Layout의 부족한 점을 채우기 위해서 나온 방식입니다.

<img src = "https://user-images.githubusercontent.com/76652929/126069543-37f9975c-eb3d-43f1-90eb-dd2a3369e1c3.png" align="center" height= "500px" width="500px" >


위의 그림과 같이 Frame-Based Layout 방식은 개발자가 직접 프레임을 계산해서 UI를 구성해야 됬습니다. 

하지만 다양한 기기의 등장으로 인해 이를 일일이 계산하는 것에 어려움을 느끼게 되었고 이를 대체하기 위해서 Auto Layout 방식이 나오게 되었습니다. 


## 2. Auto Layout 구성

![image](https://user-images.githubusercontent.com/76652929/126069685-a64c49f4-a2c6-48a5-ba8e-12d66e22d198.png)

Auto Layout은 위 그림과 같이 Constraint 즉 제약을 통해서 구성이 됩니다. 

이 제약을 나타내기 위해서 다음과 같은 식을 사용합니다.

![image](https://user-images.githubusercontent.com/76652929/126069934-bccdd335-17e9-4acc-a69f-ef68b96bf2f9.png)


item.attr = multiplier * item2.attr + constant 


![image](https://user-images.githubusercontent.com/76652929/126069819-1bfd6f5f-bcbe-48bd-ab42-e030087474b9.png)

그리고 각 제약 속성들은 위의 그림으로 간단하게 설명할 수 있습니다. 


## 3. 제약 세부 정보

centerX, centerY 는 공통된 상위뷰에 대해서 추가 됩니다. 간단하게 말하자면 전체 뷰가 아닌 자신이 속한 뷰에서 위치가 설정되는 것입니다.  

![image](https://user-images.githubusercontent.com/76652929/126070231-cee80d18-4561-4c68-8fc1-863fc01fef86.png)

leading, trailing, top, bottom 제약은 뷰의 내용 관계 없이 프레임 기준으로 정렬됩니다. 그에 반해서 Baseline 은 텍스트 기준으로 정렬이 됩니다.

이 제약들이 적용되는 데 Priority가 존재합니다. 이 Priorty 는 1000 ~ 1 의 값을 가집니다. 

1000은 필수 제약을 나타내고 그 아래는 옵션 제약이라고 합니다. 이때 Priority가 같은 것이 존재한다면 오류가 납니다. 

![image](https://user-images.githubusercontent.com/76652929/126070401-0856990d-c74a-46db-a1e3-939df1c68949.png)


옵션제약이면 @num 형식으로 나타납니다. 

또한 aspectRatio를 설정할 때는 너비 또는 높이를 계산할 수 있는 기준이 있어야 설정됩니다. 


![image](https://github.com/user-attachments/assets/e21bfacc-898d-41a7-8b41-479198c5fe70)## 목표
↓클릭  
[![image](https://github.com/user-attachments/assets/199aeb0f-c9e8-4473-aa46-5f4236b80936)](https://store.steampowered.com/app/2000280/Im_going_to_die_if_I_dont_eat_sushi/)<br/>
비슷하게 만들어보기

### 구상도
![image](https://github.com/user-attachments/assets/642dcfc5-8583-43fe-8629-191b071f339c)

### Player
![image](https://github.com/user-attachments/assets/88a11133-300b-4a7a-9124-e177f8fc542b)<br/>

#### Increase Health
![image](https://github.com/user-attachments/assets/33f5a818-c549-4155-acae-10b2da0601f3)<br/>
Hp 회복하는 함수

#### Decrease Health
![image](https://github.com/user-attachments/assets/2c7a6945-203d-4aea-8844-4a9409a16857)<br/>
Hp가 닳는 함수

#### RagDdoll
![image](https://github.com/user-attachments/assets/9afb0db7-4da1-4d47-98a7-90e2eccbaa0a)<br/>
Player가 사망 시 발동하는 함수

#### BindTime
![image](https://github.com/user-attachments/assets/8fc32bda-f4ff-4f73-b879-4a63eb65da25)<br/>
Decrease Health를 이용해 1초 마다 Hp가 닳는 Custom Evenet

### Score Component
게임의 점수를 관리하는 Component<br>
#### BeginPlay
![image](https://github.com/user-attachments/assets/d8f01704-3db3-4ea4-945e-615538cc454b)
점수와 Player를 정의하고 저장한다.<br/>

#### ScoreUp
![image](https://github.com/user-attachments/assets/709894f4-16dd-467a-a43f-c5f3da0596b2)
점수를 올려주는 함수, 100점 단위로 Hp를 회복시킨다.<br/>

#### Increase Ball
![image](https://github.com/user-attachments/assets/afedca36-8e4a-4186-a3f4-4430a124b5eb)
게임을 클리어 할 아이템을 획득 시 사용되는 함수, 7개를 획득하면 게임이 끝이 난다<br/>

### Item(Bread)
![image](https://github.com/user-attachments/assets/9aabbb8b-5e2d-4ad8-9f29-d4a3499e63bc)
Item들의 부모가 되는 Actor<br/>
Mesh는 자식에서 결정하게 한다.
#### Beginoverlap
![image](https://github.com/user-attachments/assets/a224fcec-00f2-4df8-99ae-09daed301905)<br/>
Player와 Overlap시 Player의 Hp를 회복시킨다.

### VictoryItem
![image](https://github.com/user-attachments/assets/1c76a2b1-d385-4db5-9433-d7b3a5d18e23)
VictoryItem들의 부모가 되는 Actor<br/>
위와 동일하게 자식에서 Mesh는 자식에서 결정하게 한다
#### BeginOverlap
![image](https://github.com/user-attachments/assets/7d9ca29a-b314-49b6-88eb-a2e66369ce48)
Player의 Hp를 회복시키는 동시에 Increase Ball 함수를 사용하여 게임 승리에 한 발짝 다가가게 한다.

### Gamemode
![image](https://github.com/user-attachments/assets/a82d20d2-dc56-4cdc-94c1-76459731cf70)
Tick을 통해 매 시간 Player과 게임을 클리어 했는지 확인한다.<br/>

### UI
#### WB_PlayerHealth
![image](https://github.com/user-attachments/assets/31de676c-aaee-4030-bafd-e7e51b423f76)
좌상단에는 VictoryItem을 얼마나 먹었는지 표시하게 해주었으며, 중심부는 Player HP을 우상단에는 점수를 표시하였다.<br/>

#### PreConstruct
![image](https://github.com/user-attachments/assets/571752b4-592f-40c8-a20e-4497f494c8f4)
Hp바의 Material안 Scalar 값을 1로 정해놓는다

#### Construct
![image](https://github.com/user-attachments/assets/a5e2ae67-f257-4d56-b4b1-2b4d26ea5d2b)
Player와 VictoryItem들의 Image들을 배열로 저장을한다.

#### Tick
![image](https://github.com/user-attachments/assets/30b8284e-761d-4c7f-a247-358bd6cca878)
Tick을 통해 상시 Player의 Hp 값을 검사하고 점수와 VictoryItem 이미지를 표시하게 한다

### 

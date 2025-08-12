# Secret Code(DoorLock)
---

## 기획

현관문의 Door Lock과 같이 비밀번호를 설정하고, 비밀번호를 맞게 입력하면 OK 표시가 나타나고, 비밀 번호를 틀리게 입력하면 ERROR 표시와 함께 입력한 비밀번호가 지워지는 회로를 설계해 보자. 

<br>

<img src="./pds/sca01.png" alt="scmp4_t-cmp4_" style="width: 30%;">

<br>

아래 그림은 설계할 회로를 간단하게 블록으로 나타낸 것이다. 

<img src="./pds/sca02.png" alt="scmp4_t-cmp4_" style="width: 80%;">
<BR><BR>


번호의 입력은 장비에 구성되어 있는 KEYPADS를 사용할 것이기 때문에, 이 KEYPADS를 제어하는 블록과 키패드에 의해 4자리의 값을 입력하는 SECRET SET과 KEY SET 블록, SEGMENT에 DIPLAY하는 블록, 설정된 비밀 번호와 입력하는 번호를 비교하는 블럭으로 설계가 된다. 

<br>

회로는 아래의 동작을 수행한다. 

- 번호의 입력은 KEYPAD를 사용한다. 

- 데이터의 출력은 7-Segment Array를 사용하며, 왼쪽 4자리를 비밀 번호 설정의 자리로 표시하고, 오른쪽의 4자리를 번호 맞추려는 키 입력으로 표시한다. 

- RESET이 눌리면 전체가 초기화 된다. 

- 비밀 번호 설정 또는 키 입력시 KEYPAD의 번호가 눌리면 한자리씩 왼쪽으로 전달되어 표시된다. 

- SET 스위치의 값이 1이면 비밀 번호를 설정하고, 0이면 키 입력으로 사용한다. 

- 키 입력 후, ENTER 버튼 스위치가 눌리면 비밀 번호와 키 입력 데이터를 비교해 맞으면 OK LED가 ON되고, 틀리면 ERROR LED가 ON되며 BUZZER가 울린다. 


<BR>

SACT 장비에서 사용하는 장치는 다음과 같다. 
<br>

|PORT NAME|CLK|
|:-:|:-:|
|HARDWARE|Main Clock|

|PORT NAME|K_R[3]|K_R[2]|K_R[1]|K_R[0]|
|:-:|:-:|:-:|:-:|:-:|
|HARDWARE|KEYPAD_R[3]|KEYPAD_R[2]|KEYPAD_R[1]|KEYPAD_R[0]|

|PORT NAME|K_C[2]|K_C[1]|K_C[0]|
|:-:|:-:|:-:|:-:|
|HARDWARE|KEYPAD_C[2]|KEYPAD_C[1]|KEYPAD_C[0]|

|PORT NAME|SET|RESET|ENTER|
|:-:|:-:|:-:|
|HARDWARE|S7|SW7|SW6|

|PORT NAME|CHK_OK|CHK_ERROR|BUZZER|
|:-:|:-:|:-:|:-:|
|HARDWARE|LED7|LED6|BUZZER|

|PORT NAME|SEG_COM[7]|SEG_COM[6]|SEG_COM[5]|SEG_COM[4]|
|:-:|:-:|:-:|:-:|:-:|
|HARDWARE|SEG_COM[7]|SEG_COM[6]|SEG_COM[5]|SEG_COM[4]|

|PORT NAME|SEG_COM[3]|SEG_COM[2]|SEG_COM[1]|SEG_COM[0]|
|:-:|:-:|:-:|:-:|:-:|
|HARDWARE|SEG_COM[3]|SEG_COM[2]|SEG_COM[1]|SEG_COM[0]|

|PORT NAME|SEG_DATA[7]|SEG_DATA[6]|SEG_DATA[5]|SEG_DATA[4]|
|:-:|:-:|:-:|:-:|:-:|
|HARDWARE|SEG_A|SEG_B|SEG_C|SEG_D|

|PORT NAME|SEG_DATA[3]|SEG_DATA[2]|SEG_DATA[1]|SEG_DATA[0]|
|:-:|:-:|:-:|:-:|:-:|
|HARDWARE|SEG_E|SEG_F|SEG_G|SEG_DP|

<br>
<br>

<img src="./pds/sca03.png" alt="scmp4_t-cmp4_" style="width: 80%;">



## [11-1. KeyPads Controller](./11-1.KEYPAD.md)

## [11-2. 4bit 4 Shift Register](./11-2.Shift_Register.md)

## [11-3. DoorLock Controller](./11-4.DoorLock_Controlelr.md)


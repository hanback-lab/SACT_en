# WATCH
---

## 기획

분과 초 가 표시되는 디지털 시계를 설계해 보자. 

시계는 일반적으로 아래 그림과 같이 시와 분이 표시된다. 

<br>

<img src="./pds/wta01.png" alt="scmp4_t-cmp4_" style="width: 60%;">

<br>

장비에서 동작시키기 위해서 좀 더 빠르게 변화할 수 있는 분과 초가 표시되는 시계를 만들어 보자.

시계의 설계는 아래 그림과 같이 COUNTER 블록과 SEGMENT DISPLAY블록으로 나누어 설계된다. 

<img src="./pds/wta02.png" alt="scmp4_t-cmp4_" style="width: 80%;">
<BR><BR>

COUNTER 블록은 1초 주기의 CLOCK을 받아서 초와 분을 카운트한다. 

SEGMENT DISPLAY 블록은 COUNTER 블록에서 출력하는 초와 분의 BCD 값을 입력 받아, 7-SEGMENT ARRAY에 표시하는 블록이다. 

<br><br>

장비에서 사용하는 장치는 다음과 같다. 

|PORT NAME|CLK|
|:-:|:-:|
|HARDWARE|Main Clock|

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

<BR><BR>

<img src="./pds/wt02.png" alt="scmp4_t-cmp4_" style="width: 80%;">
<BR><BR>


## [10-1. MOD 60 Counter](./10-1.COUNTER.md)

## [10-2. Segment Array Display Controller](./10-2.SEG_DISPLAY.md)

## [10-3. Watch (Miniute / Second )](./10-3.WATCH_.md)


# Secret Code(DoorLock)
---

## Planning

Let's design a circuit that sets a password like Door Lock and displays OK sign when the correct password is entered, and erases the entered password with ERROR sign when the incorrect password is entered.


<br>

<img src="./pds/sca01.png" alt="scmp4_t-cmp4_" style="width: 30%;">

<br>

The figure below shows a simple block diagram of the circuit to design.

<img src="./pds/sca02.png" alt="scmp4_t-cmp4_" style="width: 80%;">
<BR><BR>



Use keypad configured on the device to enter number. It is designed with block that controls keypad, secret set block and key set block that input four-digit values by keypad, block that displays to segment, and block that compares the set password with the number to be entered. 
<br>


The circuit operates as below.

- Use keypad to enter number

-  Use 7-Segment Array for data output. Four digits on the left indicates password setting digit, and four digits on the right indicates key input to match the number.

- When RESET is pressed, everything is initialized.

- When setting a password or entering a key, it is moved by one digit at a time and displayed if KEYPAD number is pressed.

- If SET switch is 1, set password. If SET switch is 0, use as key input.

- After entering the key, when ENTER button switch is pressed, compare the password and key input data.


<BR>

Devices used in SACT equipment are as below.
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


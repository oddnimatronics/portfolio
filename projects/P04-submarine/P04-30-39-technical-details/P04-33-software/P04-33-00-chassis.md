---
icon: code-square
label: P04.33.00⠀Chassis program logic
---
# :icon-code-square:⠀Chassis program logic
`Tags:` [!badge Submarine](/projects/P04-submarine.md) [!badge robot-car]()

!!!
Arduino source code (raw, uncleaned) is available on [Github](https://github.com/oddeyemotion/submarine/blob/main/Software/chassis-mounted/chassis-mounted.ino).
!!!

### Defining libraries

```c++
#include <SoftwareSerial.h>
#include <util/atomic.h>
#include <Wire.h>
```
### Defining variables
Group 1: 4 gearbox motors
```c++
#define ENLF  2
#define LF1  22 
#define LF2  23

#define ENRF  3
#define RF1  24
#define RF2  25

#define ENLB  4
#define LB1  26
#define LB2  27

#define ENRB  5
#define RB1  28
#define RB2  29
```
Group 2: Stepper motor
```c++
#define dirPin 6
#define stepPin 7

int Speed=130;
int LSpeed = Speed;
int RSpeed = Speed;
```
Group 3: Bluetooth communication
```c++
SoftwareSerial mySerial(50,51); //(TX,RX)
int command;
```

### User-defined functions
```c++
void Forward() {
	if(gyroAngleX <= -0.5) {
		RSpeed = Speed/2;
	}
	
	else if(gyroAngleX >= 0.5) {
		LSpeed = Speed/2;
	}
	
	else {
		RSpeed = Speed;
		LSpeed = Speed;
	}
	
	previousAngleX = gyroAngleX;
	calculateGyroAngleX(); 
	
	digitalWrite(LF1,LOW);
	digitalWrite(LF2,HIGH);
	analogWrite(ENLF,LSpeed);
	
	digitalWrite(LB1,LOW);
	digitalWrite(LB2,HIGH);
	analogWrite(ENLB,LSpeed);
	
	digitalWrite(RF1,LOW);
	digitalWrite(RF2,HIGH);
	analogWrite(ENRF,RSpeed);
	
	digitalWrite(RB1,LOW);
	digitalWrite(RB2,HIGH);
	analogWrite(ENRB,RSpeed);
	
	Serial.println(gyroAngleX);
}

```

### void setup()
Arduino serial communication
```c++
Serial.begin(9600);
```

Group 1: 4 gearbox motors
```c++
pinMode(ENLF,OUTPUT);
pinMode(LF1,OUTPUT);
pinMode(LF2,OUTPUT);

pinMode(ENRF,OUTPUT);
pinMode(RF1,OUTPUT);
pinMode(RF2,OUTPUT);

pinMode(ENLB,OUTPUT);
pinMode(LB1,OUTPUT);
pinMode(LB2,OUTPUT);

pinMode(ENRB,OUTPUT);
pinMode(RB1,OUTPUT);
pinMode(RB2,OUTPUT);
```

Group 2: Stepper motor
```c++
pinMode(stepPin, OUTPUT);
pinMode(dirPin, OUTPUT);
```

Group 3: Bluetooth communication
```c++
mySerial.begin(9600);
```
### void loop()
Group 3: Bluetooth communication
```c++
char i;
if (mySerial.available() > 0) {
  i = mySerial.read();
  Stop();
  LSpeed = Speed;
  RSpeed = Speed;

  switch (i) {
      case 'F':
        Forward();
        break;
		
      case 'B':
        Backward();
        break;
		
      case 'L':
        gyroAngleX = 0;
        Left();
        break;
		
      case 'R':
        gyroAngleX = 0;
        Right();
        break;
		
      case 'G':
        gyroAngleX = 0;
        forwardleft();
        break;
		
      case 'I':
        gyroAngleX = 0;
        forwardright();
        break;
		
      case 'H':
        gyroAngleX = 0;
        backleft();
        break;
		
      case 'J':
        gyroAngleX = 0;
        backright();
        break;
		
       case 'W':
        digitalWrite(dirPin, HIGH);
        temp = 1;
        break;  
		
       case 'w':
        temp = 0;
        break;   
		
      case 'U':
        digitalWrite(dirPin, LOW);
        temp = 1;
        break;
		
      case 'u':
        temp = 0;
        break; 
		
      case '0':
        Stop();
        break;
		
        //set speed
      case '1':
        Speed = 90;
        break;
		
      case '2':
        Speed = 100;
        break;
		
      case '3':
        Speed = 120;
        break;
		
      case '4':
        Speed = 130;
        break;
		
      case '5':
        Speed = 150;
        break;
		
      case '6':
        Speed = 170;
        break;
		
      case '7':
        Speed = 190;
        break;
		
      case '8':
        Speed = 210;
        break;
		
      case '9':
        Speed = 230;
        break;
		
      case 'q':
        Speed = 255;
        break;
    }      
```

|
--- | ---

<figure>
    <img src="https://64.media.tumblr.com/d103eb823dce2842c673f409f036857b/tumblr_mzx9wrdwFa1snc5kxo1_1280.gifv" alt="Credit: @transparent-angel on Tumblr">
</figure>

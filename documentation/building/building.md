
**Progress:**

<br>

 - Succeeded in making an LED blink:

 ```C++
void setup() {
pinMode(LED_BUILTIN, OUTPUT);
}
void loop() {
  // put your main code here, to run repeatedly:
digitalWrite(LED_BUILTIN, HIGH);
delay(100);
digitalWrite(LED_BUILTIN, LOW);
delay(100);
}
```

- Succeeded in serial communication using a variable resistor and LED:

 ```C++
const int analogInPin = A0;
const int analogOutPin = 9;
int sensorValue = 0;
int outputValue = 0;
void setup() {
Serial.begin(74880);
}
void loop() {
sensorValue = analogRead(analogInPin);
outputValue = map(sensorValue, 0, 1023, 0, 255);
analogWrite(analogOutPin, outputValue);
Serial.print("sensor = ");
Serial.print(sensorValue);
Serial.print("\t output = ");
Serial.println(outputValue);
delay(100);
}
```
- Succeeded controlling stepper motor with potentiometer via motor driver
```C++
#include <Stepper.h>
const int stepsPerRevolution = 200;
Stepper myStepper(stepsPerRevolution, 8, 9, 10, 11);
int stepCount = 0;
void setup() {
}
void loop() {
  // put your main code here, to run repeatedly:
int sensorReading = analogRead(A0);
int motorSpeed = map(sensorReading, 0, 1023, 0, 100);
if (motorSpeed > 0) {
  myStepper.setSpeed(motorSpeed);
  myStepper.step(stepsPerRevolution / 200);
  }
}
```
- idea became apparent that using gears to achieve a lower minimal stepping resolution could be a sensible idea
- additional idea that using a metal torque rod is better than a belt as there is less give

- using the motor driver Adafruit TB6612 board in order to test the stepper motor, having difficulty with the power supply, we believe that the boards and motor are demanding more power and therefore are not making consistent movements
 - fixed this issue by suppling the arduino board with external power supply
- issue now is trying to get the motors to micro-step with the boards and motors available
- i have 3D printed a bracket device that can be used to test the reproducibility and drift of the Nema 23 motor axis unit









|part name| function  | quantity  | build step  | obs.  |
 |---|---|---|---|---|
 |LM2596| voltage regulator  | 2  | 3  | these could be substituted by XX  |
 | Nose needle Pliers  | hold components while soldering  | 1  | all steps  | regular pliers would also work  |

<br>

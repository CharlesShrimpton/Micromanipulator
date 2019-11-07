
**Progress:**

<br>

Week 1 - getting started:
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
TEST

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
<br>
qdqwdfwq
Week 2 -
 - In the form of a table, containing part name, quantity and a couple of words on what they do. Extra points if the parts are divided according to the building steps (below)
 - Remember to include the tools necessary as well! (pliers, saw, computer, etc)  


 |part name| function  | quantity  | build step  | obs.  |
 |---|---|---|---|---|
 |LM2596| voltage regulator  | 2  | 3  | these could be substituted by XX  |
 | Nose needle Pliers  | hold components while soldering  | 1  | all steps  | regular pliers would also work  |

<br>


3. build steps:
 - Divide this section in as many subparts as you like and try to be as clear as possible. Would someone seeing the whole thing for the first time be able to build it? (it is a good exercise to oversee someone building the equipment using only your written/video/figure instructions)
 - Is a video a better way to instruct people how to use it? try to keep the file size as small as possible without compromising quality. Also reach out to us, as a good idea might be to create a different repository for the video files.  

<br>

4. Last checks before powering up/using for the first time:
 - Could people do one more check of everything before powering up things? Maybe double check that the capacitors were soldered in the proper orientation? Make sure there are no cut metal parts shorting the bottom side of the PCB? Make sure the area around the equipment is clear and won't be hit if the equipment has moving parts (eg shakers, centrifuges, etc).

# codtech-task-2
COMPANY: CODTECH IT SOLUTIONS

NAME:KUNDRAPU PAVAN KUMAR

INTERN ID:CTO4DF2138

DOMAIN: Embedded Systems

DURATION: 4 WEEKS

MENTOR: Neela Santhosh Kumar
DESCRIPTION : HC-05 Blutooth ModuleHi-Link (5V) 5V Relay - 4 Nos ATMEGA328P IC 28 Pin IC Base 16 Mhz Crystal Oscillator BC547 Transistor - 4 Nos 22pF Capacitor - 2 NosLED 5mm - 5 Nos IN4007 Diode - 5 Nos 1K Resistor - 9 Nos 2 Pin Screw Connector 3 Pin Screw Connector - 4 Nos TOOLS NEEDED Soldering Iron Soldering Wire FluxConnect Arduino Uno on PC Open Arduino IDE (Software) Then Go To Tools>Board>Select Arduino UnoSelect Correct Port Upload Code Below
CIRCUIT DIAGRAM :![WhatsApp Image 2025-07-03 at 12 24 32_d5627eff](https://github.com/user-attachments/assets/aacafea9-c79b-4ab6-ba29-8caa4143f224)
CODE:
/*
Relay IN1 connected to PinOut 2 Arduino
Relay IN2 connected to PinOut 3 Arduino
Relay IN3 connected to PinOut 4 Arduino
Relay IN4 connected to PinOut 5 Arduino
--->you can connected to relay modul 4 channel
Serial data sending from Arduino Bluetooth Relay 4CH.apk
data '1'-'4' to on is Ralay CH 1-4
data 'A'-'D' to off is Ralay CH 1-4
data '9' to on ALL CH 1-4
data 'I' to off ALL CH 1-4
*/

#define relay1 2
#define relay2 3
#define relay3 4
#define relay4 5
char val;
void setup() {
 pinMode(relay1,OUTPUT);
 pinMode(relay2,OUTPUT);
 pinMode(relay3,OUTPUT);
 pinMode(relay4,OUTPUT);
 digitalWrite(relay1,LOW);
 digitalWrite(relay2,LOW);
 digitalWrite(relay3,LOW);
 digitalWrite(relay4,LOW);
 Serial.begin(9600);
 Serial.begin(9600);
}
void loop() {
//cek data serial from bluetooth android App
if( Serial.available() >0 ) {
 val = Serial.read();
 Serial.println(val); 
}
//Relay is on
 if( val == '1' ) {
 digitalWrite(relay1,HIGH); }
 else if( val == '2' ) {
 digitalWrite(relay2,HIGH); }
 else if( val == '3' ) {
 digitalWrite(relay3,HIGH); }
 else if( val == '4' ) {
 digitalWrite(relay4,HIGH); }
 //relay all on
 else if( val == '9' ) {
 digitalWrite(relay1,HIGH);
 digitalWrite(relay2,HIGH);
 digitalWrite(relay3,HIGH);
 digitalWrite(relay4,HIGH);
}
//relay is off
 else if( val == 'A' ) {
 digitalWrite(relay1,LOW); }
 else if( val == 'B' ) {
 digitalWrite(relay2,LOW); }
 else if( val == 'C' ) {
 digitalWrite(relay3,LOW); }
 else if( val == 'D' ) {
 digitalWrite(relay4,LOW); }
 //relay all off 
 else if( val == 'I' ) {
 digitalWrite(relay1,LOW);
 digitalWrite(relay2,LOW);
 digitalWrite(relay3,LOW);
 digitalWrite(relay4,LOW);
}
}
OUTPUT :
![WhatsApp Image 2025-07-03 at 12 24 33_3b07ffa8](https://github.com/user-attachments/assets/0734ec34-83f1-46f5-848c-b2d93d0d47bd)
![WhatsApp Image 2025-07-03 at 12 24 33_225fd8d6](https://github.com/user-attachments/assets/221b4ef1-5e69-4e9f-bf28-bc558ce763d0)
![WhatsApp Image 2025-07-03 at 12 24 33_119521ec](https://github.com/user-attachments/assets/3a23d588-b7e1-45ea-ab0b-77d532bb7639)
WORKING DEMO :

https://www.youtube.com/watch?v=OmyzJ_P9TJs

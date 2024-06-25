#include <Servo.h>
Servo myServo;
const int servoPin1 = 9;

const int irValue1 = 7;//gate 
const int irValue2 = 8;//parking A
//const int irValue3 = 9;//parking B

void setup(){
  myServo.attach(servoPin1);
  Serial.begin(9600);
  pinMode(irValue1,INPUT);
  pinMode(irValue2,INPUT);
  //pinMode(irValue3,INPUT);
}
void loop(){
  int Gate = digitalRead(irValue1);
  int parkingA = digitalRead(irValue2);

  if(parkingA == HIGH && Gate ==LOW){
    myServo.write(170);//Adjust the angle according to you 
    delay(3000);
    //Serial.println("welcome")
  }
  else{
    myServo.write(30);//Adjust the angle according to you 
  }
}

  

#include <LiquidCrystal.h>

#include <dht.h>
#define ECHOPIN 6       // Pin to receive echo pulse 
#define TRIGPIN 7        // Pin to send trigger pulse
LiquidCrystal lcd(8,9,10,11,12,13); 

  void forward()
{
  digitalWrite(2,HIGH);
  digitalWrite(3,LOW);
  digitalWrite(4,HIGH);
  digitalWrite(5,LOW);
  
}
void back()
{
  digitalWrite(2,LOW);
  digitalWrite(3,HIGH);
  digitalWrite(4,LOW);
  digitalWrite(5,HIGH);
  
}
void left()
{
  digitalWrite(2,LOW);
  digitalWrite(3,LOW);
  digitalWrite(4,HIGH);
  digitalWrite(5,LOW);
  
}
void right()
{
  digitalWrite(2,HIGH);
  digitalWrite(3,LOW);
  digitalWrite(4,LOW);
  digitalWrite(5,LOW);
}
void stp()
{
  digitalWrite(2,LOW);
  digitalWrite(3,LOW);
  digitalWrite(4,LOW);
  digitalWrite(5,LOW);
}
void setup() 
{ 
   lcd.begin(16, 2);
  lcd.print("distance");
  Serial.begin(9600);
  pinMode(ECHOPIN, INPUT); 
  pinMode(TRIGPIN, OUTPUT); 
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
}
void loop() 
{ 
 
     
      // Start Ranging -Generating a trigger of 10us burst 
digitalWrite(TRIGPIN, LOW); 
  delayMicroseconds(2); 
  digitalWrite(TRIGPIN, HIGH); 
  delayMicroseconds(10); 
  digitalWrite(TRIGPIN, LOW);
  // Distance Calculation
  
  float distance = pulseIn(ECHOPIN, HIGH); 
  distance= distance/58; 
/* The speed of sound is 350 m/s or 29 us per cm.The Ultrasonic burst travels out & back.So to find the distance of object we divide by 58  */
  Serial.print(distance); 
  Serial.println(" cm");
  delay(200);
    lcd.setCursor(0,1);
 lcd.println(distance);

  if (distance<=40)
  {
     digitalWrite(2,LOW);
        digitalWrite(3,LOW);
        digitalWrite(4,LOW);
        digitalWrite(5,LOW);
  }
  
   char data=Serial.read();
    if (data=='F')
    {
      Serial.println("forward");
      forward(); 
    }
    else if (data=='B')
    {
      Serial.println("back");
      back(); 
    }
    else if (data=='L')
    { 
      Serial.println("left");
      left();
    }
    else if (data=='R')
    {
      Serial.println("right");
      right();
    }
    else if (data=='S')
    {
       Serial.println("stp");
       stp();
    }

  }



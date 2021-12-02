#include<LiquidCrystal.h>
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
int val;
int tempPin = 0;

void setup()
{
 lcd.begin(16, 2); 
}

void loop()
{
  val = analogRead(tempPin);
  float mv = ( val/1024.0)*5000; 
  float cel = mv/10;
  float farh = (cel*9)/5 + 32;
  
  lcd.setCursor(0,0);          
  lcd.print("TEMPRATURE = "); 
  lcd.setCursor(1,1);           
  lcd.print(cel);    
  delay(1000);
  lcd.clear();
  
}

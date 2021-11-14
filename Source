long hour = 3600000; //3600000 milliseconds in an hour
long minute = 60000; //60000 milliseconds in a minute
long second = 1000; //1000 milliseconds in a second
int k = 0;
int g = 1; //a variable that toggle between Celsius & Fahrenheit
int i = 0; //a variable to toggle between clock and temp:
long addition = 0;// this will be use as an addition to add the time
//BA, BB, BC, BD, BE are the corresponding push button
int pbA = 6; //SWITCH BETWEEN CLOCK AND TEMPERATURE MODE
int pbB = 5; //increments hours & switches between C and F
int pbC = 4; //decrements hours
int pbD = 3; //increments minutes
int pbE = 2; //decrements minutes
// defind the lcd and the pin that are used

#include <LiquidCrystal.h>
int tempPin = 0;
LiquidCrystal lcd(7, 8, 9, 10, 11, 12);
// setting up my push button as input_pullup
void setup() {
pinMode (pbA, INPUT_PULLUP);
pinMode (pbB, INPUT_PULLUP);
pinMode (pbC, INPUT_PULLUP);
pinMode (pbD, INPUT_PULLUP);
pinMode (pbE, INPUT_PULLUP);
Serial.begin (57600);

lcd.begin(16, 2); // Set the lcd column and row:
}// end the set:
void temp() {
if(digitalRead(pbB)==LOW)
{
 if(g==1)
{
 g=0;
}
else if(g==0)
{
 g=1;
}
delay(100);
}
else
{
g=g;
}
Serial.println(g);
int tempReading = analogRead(tempPin);
// This is OK
double tempK = log(10000.0 * ((1024.0 / tempReading - 1)));
tempK = 1 / (0.001129148 + (0.000234125 + (0.0000000876741 * tempK * tempK )) * tempK ); // Temp Kelvin
float tempC = tempK - 273.15; // Convert Kelvin to Celcius
float tempF = (tempC * 9.0)/ 5.0 + 32.0; // Convert Celcius to Fahrenheit
float tempVolts = tempReading * 5.0 / 1024.0;

 tempC = (tempVolts - 0.5) * 10.0;
 tempF = tempC * 9.0 / 5.0 + 32.0;
// Display Temperature in C
lcd.setCursor(0, 0);
if(g==0)
{
lcd.print("Temp C ");
lcd.setCursor(6, 0);
// Display Temperature in C
lcd.print(tempC);
 Serial.print("Temp C ");
 // Serial.setCursor(6, 0);
 Serial.print(tempC);
}
if (g==1){
 lcd.print("Temp F ");
 lcd.setCursor(6, 0);
 // Display Temperature in F
 lcd.print(tempF);
 Serial.print("Temp F ");
// Serial.setCursor(6, 0);
 Serial.print(tempF);
}
delay(500);
}
void time (){ //void time will be used to call the time
 long timeNow = millis() + hour;
Serial.print(addition);
Serial.println();

timeNow = timeNow+addition;
Serial.print(timeNow);
Serial.println();
int hours = timeNow/ hour; // this is the number of hours:
Serial.println(hours);
Serial.println(hours*hour);
if(hours >12)
{
 hours = hours%12;
}
else if (hours <1)
{
 addition = 360000012;
 Serial.print("hello");
}

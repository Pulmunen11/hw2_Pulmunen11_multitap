# hw2_Pulmunen11_multitap
Text entry device using Arduino IDE, RedBear Duo and 9 switches

/*
Multitap text-entry device for RedBear Duo
Each time input pin goes from LOW to HIGH, one character is selected form a string of characters
and output in serial monitor if input pin D4 is toggled from LOW to HIGH.
 
 The circuit:
 * nine pushbuttons attached from D0–D4 and D8-D11 to +3v3 (uses internal pulldown)

 created 21 November 2006
 by David A. Mellis for Arduino
 modified 30 Aug 2011
 by Limor Fried
 modified 28 Dec 2012
 by Mike Walters
 modified 29 Aug 2016
 by Bjoern Hartmann for RedBear Duo
 modified 10 Sep 2016
 by Maija Hynninen
 
 */

// do not use the cloud functions - assume programming through Arduino IDE
#if defined(ARDUINO) 
SYSTEM_MODE(MANUAL); 
#endif

// constants won't change. They're used here to
// set pin numbers:
const int button1Pin = D0;    // the number of the pushbutton pin
const int button2Pin = D1;
const int button3Pin = D2;
const int button4Pin = D3;

const int button5Pin = D4;

const int button6Pin = D8;
const int button7Pin = D9;
const int button8Pin = D10;
const int button9Pin = D11;


String hello1String = "efgh"; //strings with data for each buttons D0-D3 and D8-D11
int string1Pos = -1;
String hello2String = "mnop";
int string2Pos = -1;
String hello3String = "uvwx";
int string3Pos = -1;
String hello4String = " 0123456789";
int string4Pos = -1;


String hello6String = "abcd";
int string6Pos = -1;
String hello7String = "ijkl";
int string7Pos = -1;
String hello8String = "qrst";
int string8Pos = -1;
String hello9String = "yz?!";
int string9Pos = -1;




void setup() {
  pinMode(button1Pin, INPUT_PULLDOWN);
  pinMode(button2Pin, INPUT_PULLDOWN);
  pinMode(button3Pin, INPUT_PULLDOWN);
  pinMode(button4Pin, INPUT_PULLDOWN);
  
  pinMode(button5Pin, INPUT_PULLDOWN);
  
  pinMode(button6Pin, INPUT_PULLDOWN);
  pinMode(button7Pin, INPUT_PULLDOWN);
  pinMode(button8Pin, INPUT_PULLDOWN);
  pinMode(button9Pin, INPUT_PULLDOWN);

  Serial.begin(9600);


}



void loop() {
  
  
int button1State, button2State, button3State, button4State, button5State, button6State, button7State, button8State, button9State; 

button1State = digitalRead(button1Pin);
button2State = digitalRead(button2Pin);
button3State = digitalRead(button3Pin);
button4State = digitalRead(button4Pin);

button5State = digitalRead(button5Pin);

button6State = digitalRead(button6Pin);
button7State = digitalRead(button7Pin);
button8State = digitalRead(button8Pin);
button9State = digitalRead(button9Pin);



if (button1State == HIGH){    //press character button
  string1Pos++;
  delay (200);
}

  if (button5State == HIGH){  //press enter

    int current1Pos = string1Pos; 
    Serial.print(hello1String.charAt(current1Pos));
    string1Pos = -1;

 
  delay (100);

}

if (button2State == HIGH){
  string2Pos++;
  delay (200);
}

   if (button5State == HIGH){
    int current2Pos = string2Pos;
    Serial.print(hello2String.charAt(current2Pos));
    string2Pos = -1;

    delay (100);
  }

if (button3State == HIGH){
  string3Pos++;
  delay (200);
}

  if (button5State == HIGH){
    int current3Pos = string3Pos;
    Serial.print(hello3String.charAt(current3Pos));
    string3Pos = -1;

    delay (100);
  }

  if (button4State == HIGH){
  string4Pos++;
  delay (200);
}

  if (button5State == HIGH){
    int current4Pos = string4Pos;
    Serial.print(hello4String.charAt(current4Pos));
    string4Pos = -1;

    delay (100);
  }

  
if (button6State == HIGH){
  string6Pos++;
  delay (200);
}

  if (button5State == HIGH){

    int current6Pos = string6Pos; 
    Serial.print(hello6String.charAt(current6Pos));
    string6Pos = -1;

 
  delay (100);

}

if (button7State == HIGH){
  string7Pos++;
  delay (200);
}

  if (button5State == HIGH){

    int current7Pos = string7Pos; 
    Serial.print(hello7String.charAt(current7Pos));
    string7Pos = -1;

 
  delay (100);

}

if (button8State == HIGH){
  string8Pos++;
  delay (200);
}

  if (button5State == HIGH){

    int current8Pos = string8Pos; 
    Serial.print(hello8String.charAt(current8Pos));
    string8Pos = -1;

 
  delay (100);

}

if (button9State == HIGH){
  string9Pos++;
  delay (200);
}

  if (button5State == HIGH){

    int current9Pos = string9Pos; 
    Serial.print(hello9String.charAt(current9Pos));
    string9Pos = -1;

 
  delay (100);

}
  

}




  




# Fire-Detection-System
const int buzzerPin = 12; 
const int flamePin = 11; 
int Flame = HIGH; 
int redled = 5; 
int greenled = 6; 
int relay = 9; 
void setup() 
{ 
  pinMode(buzzerPin, OUTPUT); 
  pinMode(redled, OUTPUT); 
  pinMode(greenled, OUTPUT); 
  pinMode(relay, OUTPUT); 
  pinMode(flamePin, INPUT); 
  Serial.begin(9600); 
} 
void loop() 
{ 
  Flame = digitalRead(flamePin); 
  if (Flame== LOW) 
  { 
    Serial.println("ATD0123456789;");     //Insert phone number here
    digitalWrite(buzzerPin, HIGH); 
    digitalWrite(redled, HIGH); 
    digitalWrite(greenled, LOW); 
    digitalWrite(relay,LOW);
    Serial.println("AT+CMGF=1"); //Sets the GSM Module in Text Mode 
    delay(1000); // Delay of 1 second 
    Serial.println("AT+CMGS=\"+91x\"\r"); // Replace x with mobile number 
    Serial.println("FIRE IN THE HOUSE");// The SMS text you want to send 
    Serial.println((char)26); // ASCII of CTRL+Z for saying the end of sms to the module
  } 
  else 
  { 
    digitalWrite(buzzerPin, LOW); 
    digitalWrite(greenled, HIGH); 
    digitalWrite(redled, LOW); 
    digitalWrite(relay, HIGH); 
  }
}

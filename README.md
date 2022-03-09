int pirSensor =3;
int relay1= 5;
void setup() 
{
  Serial.begin(115200);
  pinMode(relay1,OUTPUT);
  pinMode(relay1,OUTPUT);
}

void loop()
{
  int sensorValue= digitalRead(pirSensor);
  while(sensorValue==1)
  {
      digitalWrite(relay1,HIGH);
      Serial.println("HIGH");
      delay(1000);
      sensorValue=digitalRead(pirSensor); 
      if(sensorValue==1)
      {
          break;
      }
      else
      {
        delay(2000);
        digitalWrite(relay1,LOW);
        Serial.println("LOW");
      }
  }

}

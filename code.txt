// C++ code
//
int pirsensor = 0;

void setup()
{
  pinMode(A0, INPUT);
  Serial.begin(9600);
  pinMode(7, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(10, OUTPUT);
}

void loop()
{
  pirsensor = analogRead(A0);
  Serial.println(pirsensor);
  if (pirsensor >= 100) {
    digitalWrite(7, LOW);
    digitalWrite(6, HIGH);
    digitalWrite(10, HIGH);
  } else {
    digitalWrite(7, HIGH);
    digitalWrite(6, LOW);
    digitalWrite(10, LOW);
  }
  delay(10); // Delay a little bit to improve simulation performance
}
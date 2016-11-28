int Trig=4;
int Echo=5;
void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);//初始化串口通信，并将波特率设置为9600
  pinMode(Trig, OUTPUT);
  pinMode(Echo, INPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  int m;
  digitalWrite(Trig,LOW);
  delayMicroseconds(2);
  digitalWrite(Trig,HIGH);
  delayMicroseconds(10);
  digitalWrite(Echo,LOW);
  m=pulseIn(Echo,HIGH);
  m=m*0.018;
  Serial.print(m);
  Serial.print("cm");
  Serial.println();
  delay(1000);
}

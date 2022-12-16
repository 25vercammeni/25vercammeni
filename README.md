Servo myservo1;
Servo myservo2;
Servo myservo3;
Servo myservo4;
Servo myservo5;
Servo myservo6;

int potpin = A0;
int potpin1 = A1;
int potpin2 = A2;
int potpin3 = A3;
int potpin4 = A4;
int potpin5 = A5;
int val;

void setup()
{
  myservo1.attach(3);
  myservo2.attach(5);
  myservo3.attach(9);
  myservo4.attach(10);
  myservo5.attach(11);
  myservo6.attach(6);
}

void loop()
{
  val = analogRead(potpin);
  val = map(val, 0, 1023, 0, 250);
  myservo1.write(val);
  delay(15);

  val = analogRead(potpin1);
  val = map(val, 0, 1023, 0, 250);
  myservo2.write(val);
  delay(15);

  val = analogRead(potpin2);
  val = map(val, 0, 1023, 0, 250);
  myservo3.write(val);
  delay(15);

  val = analogRead(potpin3);
  val = map(val, 0, 1023, 0, 250);
  myservo4.write(val);
  delay(15);

  val = analogRead(potpin4);
  val = map(val, 0, 1023, 0, 250);
  myservo5.write(val);
  delay(15);

  val = analogRead(potpin5);
  val = map(val, 0, 1023, 0, 250);
  myservo6.write(val);
  delay(15);Servo baseYaw;
Servo basePitch;
Servo elbow;
Servo wristPitch;
Servo wristRoll;

int valBaseYaw = 90 ; //Initial angle
int valBasePitch = 90; //Initial angle
int valelbow = 90; //Initial angle
int valwristPitch = 90; //Initial angle
int valwristRoll = 90; //Initial angle

void setup() {
 baseYaw.attach(2); //Servo Pin
 pinMode (22, INPUT); //Clockwise pin
 pinMode(23, INPUT); //Counterclockwise pin

 basePitch.attach(3); //Servo Pin
 pinMode (24, INPUT); //Clockwise pin
 pinMode(25, INPUT); //Counterclockwise pin

 elbow.attach(4); //Servo Pin
 pinMode (26, INPUT); //Clockwise pin
 pinMode(27, INPUT); //Counterclockwise pin

 wristPitch.attach(5); //Servo Pin
 pinMode (28, INPUT); //Clockwise pin
 pinMode(29, INPUT); //Counterclockwise pin

 wristRoll.attach(6); //Servo Pin
 pinMode (30, INPUT); //Clockwise pin
 pinMode(31, INPUT); //Counterclockwise pin
}

void loop() {

 if ((digitalRead(22) == HIGH) && (valBaseYaw != 175))
 {
 valBaseYaw = valBaseYaw + 1; //For Clockwise button
 }
 if ((digitalRead(23) == HIGH) && (valBaseYaw != 0))
 {
 valBaseYaw = valBaseYaw - 1; //For Counterclockwise button
 }
 baseYaw.write(valBaseYaw); //Let the magic works!

 if ((digitalRead(24) == HIGH) && (valBasePitch != 175))
 {
 valBasePitch = valBasePitch + 1; //For Clockwise button
 }
 if ((digitalRead(25) == HIGH) && (valBasePitch != 0))
 {
 valBasePitch = valBasePitch - 1; //For Counterclockwise button
 }
 basePitch.write(valBasePitch); //Let the magic works!

 if ((digitalRead(26) == HIGH) && (valelbow != 175))
 {
 valelbow = valelbow + 1; //For Clockwise button
 }
 if ((digitalRead(27) == HIGH) && (valelbow != 0))
 {
 valelbow = valelbow - 1; //For Counterclockwise button
 }
 elbow.write(valelbow); //Let the magic works!

 if ((digitalRead(28) == HIGH) && (valwristPitch != 175))
 {
 valwristPitch = valwristPitch + 1; //For Clockwise button
 }
 if ((digitalRead(29) == HIGH) && (valwristPitch != 0))
 {
 valwristPitch = valwristPitch - 1; //For Counterclockwise button
 }
 wristPitch.write(valwristPitch); //Let the magic works!

 if ((digitalRead(30) == HIGH) && (valwristRoll != 175))
 {
 valwristRoll = valwristRoll + 1; //For Clockwise button
 }
 if ((digitalRead(31) == HIGH) && (valwristRoll != 0))
 {
 valwristRoll = valwristRoll - 1; //For Counterclockwise button
 }
 wristRoll.write(valwristRoll); //Let the magic works!

 delay(10); // General Speed
}

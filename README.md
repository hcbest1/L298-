# L298-

// C++ code
//
#define IN1  4
#define IN2  5
#define ENR  9

#define IN3  2
#define IN4  3
#define ENL  10


void setup()
{
   pinMode(LED_BUILTIN, OUTPUT);
   pinMode(IN1, OUTPUT);
   pinMode(IN2, OUTPUT);
   pinMode(IN3, OUTPUT);
   pinMode(IN4, OUTPUT);
   pinMode(ENL, OUTPUT);
   pinMode(ENR, OUTPUT);


}

void motor_1(int speed)
{
  if(speed >=0)
  {
     digitalWrite(IN1, LOW);
     digitalWrite(IN2, HIGH);
     analogWrite(ENL, speed);   // 0-255
  }
  else
  {
     digitalWrite(IN1, HIGH);
     digitalWrite(IN2, LOW);
     analogWrite(ENL, -speed);
  }
}

void motor_r(int speed)
{
  if(speed >=0)
  {
     digitalWrite(IN3, LOW);
     digitalWrite(IN4, HIGH);
     analogWrite(ENR, speed);   // 0-255
  }
  else
  {
     digitalWrite(IN3, HIGH);
     digitalWrite(IN4, LOW);
     analogWrite(ENR, -speed);
  }
}

void loop()
{
   motor_1(-30);
   motor_r(40);
}

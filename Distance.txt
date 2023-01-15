#define trigPin 4
#define echoPin 2
long sure, mesafe

void setup () {
Serial.begin(9600);
pinMode(trigPin, OUTPUT);
pinMode(echoPin, INPUT);


Serial.println("Arduino İle Mesafe Sensörü Uygulaması Başlatılıyor...");
delay(3000);
}

void loop () {
digitalWrite(trigPin, LOW);
delayMicroseconds(3);
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);


sure = pulseIn(echoPin, HIGH);


mesafe = (sure/2) * 0.0343;
Serial.print(mesafe);
Serial.println(" cm uzaklıkta");
delay(500);
}
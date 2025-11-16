# workshop-week-4

For this workshop we are using ultrasonic sensor to measure the 
distance of nearby objects. 
> Required materials:-

i. Arduino Board

ii. Ultrasonic Sensor 

iii. LEDs

iv. Jumper Wires

> ### Steps
> Connect the Ultrasonic Sensor (HC-SR04)
> - VCC → 5V on Arduino
> - GND → GND on Arduino
> - Trig → Digital Pin 9
> - Echo → Digital Pin 10
**Code** 
```
 // trig pin of ultrasonic sensor
 // echo pin of ultrasonic sensor
 // LED pin
 // variable to store time duration of ultrasonic wave to transmit and receive sound
 // variable to store the distance after calculation

void setup() {
// put your setup code here, to run once
  pinMode(ledPin, OUTPUT);
  Serial.begin(9600); // initialize the serial monitor
}

void loop() {
  // put your main code here, to run repeatedly
  // Send ultrasonic pulse
  digitalWrite(trigPin, LOW);
  delayMicroseconds(2);
  digitalWrite(trigPin, HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin, LOW);
  
  // Read echo time
  duration = pulseIn(echoPin, HIGH);
  
  // Calculate distance in cm
  distance = duration * 0.034 / 2; // formula to convert the ultrasonic time into centimeters
  
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  
  // Turn on LED if object is close
  if (distance < 10) {
    digitalWrite(ledPin, HIGH);
  } else {
    digitalWrite(ledPin, LOW);
  }
  
  delay(500);
}

```
### Task 
```
Connect the ultrasonic sensor as per the guide and write the learning reflection.


```

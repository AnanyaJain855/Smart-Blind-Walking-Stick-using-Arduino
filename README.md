# Smart Blind Walking Stick using Arduino

A cost-effective and functional walking stick designed to assist visually impaired individuals using Arduino and ultrasonic technology. It detects nearby obstacles and alerts the user via buzzer, LED, and vibrations.

## 🎯 Objective

To develop a smart walking stick that can alert visually impaired individuals to nearby obstacles, thereby helping them navigate safely and independently.

## 🛠️ Components Used

- Arduino Uno
- HC-SR04 Ultrasonic Sensor
- Buzzer
- Vibration Motor
- LED with 220Ω resistor
- Jumper Wires
- PVC Pipe 
- Battery Holder & Rechargeable Battery
- Cable Ties

## ⚙️ Working Principle

The stick uses an ultrasonic sensor to detect obstacles up to a distance of 25 cm. When an object is detected:
- The buzzer beeps
- The LED lights up
- The vibration motor activates

These alerts notify the user of nearby obstructions, helping them avoid collisions.

## 📋 Circuit Diagram
![1](https://github.com/user-attachments/assets/bbd3a369-4cca-4321-aac9-0760cf722921)


## 📄 Code

```cpp
// defines pins numbers
const int trigPin = 9;
const int echoPin = 10;
const int buzzer = 11;
const int ledPin = 13;

// defines variables
long duration;
int distance;
int safetyDistance;


void setup() {
pinMode(trigPin, OUTPUT); // Sets the trigPin as an Output
pinMode(echoPin, INPUT); // Sets the echoPin as an Input
pinMode(buzzer, OUTPUT);
pinMode(ledPin, OUTPUT);
Serial.begin(9600); // Starts the serial communication
}


void loop() {
// Clears the trigPin
digitalWrite(trigPin, LOW);
delayMicroseconds(2);

// Sets the trigPin on HIGH state for 10 micro seconds
digitalWrite(trigPin, HIGH);
delayMicroseconds(10);
digitalWrite(trigPin, LOW);

// Reads the echoPin, returns the sound wave travel time in microseconds
duration = pulseIn(echoPin, HIGH);

// Calculating the distance
distance= duration*0.034/2;

safetyDistance = distance;
if (safetyDistance <= 5){
  digitalWrite(buzzer, HIGH);
  digitalWrite(ledPin, HIGH);
}
else{
  digitalWrite(buzzer, LOW);
  digitalWrite(ledPin, LOW);
}

// Prints the distance on the Serial Monitor
Serial.print("Distance: ");
Serial.println(distance);
}
```

## 📊 Results

When an obstacle is detected within 25 cm:
- The LED lights up
- The buzzer beeps
- The user is alerted effectively

No alert is triggered if the path is clear.


## 🚀 Future Improvements

- Add water detection sensor
- Implement GPS tracking
- Develop a mobile app companion
- Add voice feedback system


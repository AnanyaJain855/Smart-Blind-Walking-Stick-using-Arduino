# Smart-Blind-Walking-Stick-using-Arduino
A cost-effective and functional walking stick designed to assist visually impaired individuals using Arduino and ultrasonic technology. It detects nearby obstacles and alerts the user via buzzer, LED, and vibrations.

Objective:
To develop a smart walking stick that can alert visually impaired individuals to nearby obstacles, thereby helping them navigate safely and independently.

Components Used:
•	Arduino Uno
•	HC-SR04 Ultrasonic Sensor
•	Buzzer
•	Vibration Motor
•	LED with 220Ω resistor
•	Jumper Wires
•	PVC Pipe
•	Battery Holder & Rechargeable Battery
•	Cable Ties

Working Principle:
The stick uses an ultrasonic sensor to detect obstacles up to a distance of 25 cm. When an object is detected:
•	The buzzer beeps.
•	The LED lights up.
•	The vibration motor activates (inferred from report, although not coded in the current version).
These alerts notify the user of nearby obstructions, helping them avoid collisions.

Result:
When an obstacle is detected within 25 cm:
•	The LED lights up,
•	The buzzer beeps,
•	And the user is alerted effectively.
No alert is triggered if the path is clear.

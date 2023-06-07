# EXP_4
EXPERIMENT-NO--04-Distance measurement using Ultrasonic sensor

AIM:
To interface an ultrasonic pair and measure the distance in centimeters , calculate the error

COMPONENTS REQUIRED:
1. ultrasonic sensor module HC-SR04
2. 1 KΩ resistor
3. Arduino Uno
4. USB Interfacing cable
5. Connecting wires

THEORY:
The HC-SR04 ultrasonic sensor uses SONAR to determine the distance of an object just like the bats
do. It offers excellent non-contact range detection with high accuracy and stable readings in an easyto-use package from 2 cm to 400 cm or 1” to 13 feet.
The operation is not affected by sunlight or black material, although acoustically, soft materials like
cloth can be difficult to detect. It comes complete with ultrasonic transmitter and receiver module.
Technical Specifications Power Supply − +5V DC Quiescent Current − <2mA Working Current − 15mA
Effectual Angle − <15° Ranging Distance − 2cm – 400 cm/1″ – 13ft Resolution − 0.3 cm Measuring
Angle − 30 degree
The ultrasonic sensor uses sonar to determine the distance to an object. Here’s what happens:
The ultrasound transmitter (trig pin) emits a high-frequency sound (40 kHz). The sound travels
through the air. If it finds an object, it bounces back to the module. The ultrasound receiver (echo
pin) receives the reflected sound (echo). The time between the transmission and reception of the
signal allows us to calculate the distance to an object. This is possible because we know the sound’s
velocity in the air. Here’s the formula:
distance to an object = ((speed of sound in the air)*time)/2 speed of sound in the air at 20ºC (68ºF) =
343m/s

FIGURE 01 CIRCUIT OF INTERFACING ULTRASONIC SENSOR
![image](https://github.com/Balaramansethu/Ex.-04---Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/96691241/f32095fe-5b68-451b-b495-97514d30f3b3)

PROCEDURE:
1. Connect the circuit as per the circuit diagram
2. Connect the board to your computer via the USB cable.
3. If needed, install the drivers.
4. Launch the Arduino IDE.
5. Select the board (If you the board is arduino uno, select accordingly).
6. Select your serial port, accordingly ( E.g. COM5 )
7. Open the file of the program and verify the error , clear if any errors that are existing
8. Upload the program and check for the physical working.
9. Ensure safety before powering up the device
10. Plot the graph for the output voltage vs the resistance

PROGRAM
#define echoPin 9
#define trigPin 10
long duration;
int distance;
void setup()
{
 pinMode(trigPin, OUTPUT);
 pinMode(echoPin, INPUT);
 Serial.begin(9600);
}
void loop()
{
 digitalWrite(trigPin, LOW);
 delayMicroseconds(2);
 digitalWrite(trigPin, HIGH);
 delayMicroseconds(10);
 digitalWrite(trigPin, LOW);
 duration=pulseIn(echoPin,HIGH);
 distance=duration*0.034/2;
 Serial.print("Distance: ");
 Serial.print(distance);
 Serial.println("cm"); }

OUTPUT:
Before Simulation:
![image](https://github.com/Balaramansethu/Ex.-04---Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/96691241/80406cfd-3d87-4db4-9949-d1b722d3052a)

After Simulation:
![image](https://github.com/Balaramansethu/Ex.-04---Interfacing-digital-output-with-arduino-ultrasonic-sensor/assets/96691241/ce7bf5e0-4394-4e4a-b69f-5bd9aa4215d3)

RESULTS
The Ultrasonic sensor is used to measure the distance successfully

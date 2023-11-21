# Personal-Snoezelen-Device
Personal Snoezelen Device for dementia patients

## About the project

![Capture](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/4b4fc18e-9d80-4859-b553-6541323fa571)

The idea for the project consists of applying the concept of Snoezelen chambers to treat dementia patients at home with a device.

A Snoezelen chamber is a therapeutic space designed to provide a controlled and calming environment for individuals with sensory processing difficulties or developmental disabilities. Equipped with various sensory elements such as specialized lighting, sounds, tactile objects, and visual displays, the Snoezelen chamber aims to stimulate the senses and promote relaxation, exploration, and sensory integration. It is commonly used in healthcare, educational, and care settings to reduce anxiety, improve mood, enhance sensory awareness, and support self-regulation.

Bringing the experience of a Snoezelen chamber home was the main idea behind the project. To accomplish the goal, a device was needed.
The device was equipped with speakers, LEDs, and a vapor generator. These actuators will work randomly to captivate the attention of the patient.

Because the device is for home use, it was mandatory to find a case to disguise all its components, something that can easily pass as something that can be found in a normal house. In many rooms what is very common to find is a vase, which perfectly fits with the purpose of our project, because it can contain a liquid that is necessary for the vapor generator and also can contain the speakers, the ultrasonic sensor, and the RGB LEDs.

https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/288885db-be2c-419c-b9b4-cbccb0a7c5fc

## The Code Explanation 

Libraries

Adafruit_NeoPixel.h: This library is used to control NeoPixel LED strips.
Servo.h: This library is used to control servo motors.

NeoPixel Setup

#define NEOPIXEL_PIN 6
#define NEOPIXEL_NUMPIXELS 8

Adafruit_NeoPixel strip = Adafruit_NeoPixel(NEOPIXEL_NUMPIXELS, NEOPIXEL_PIN, NEO_GRB + NEO_KHZ800);
Here, the NeoPixel LED strip is set up. It specifies that the strip is connected to pin 6, and there are 8 pixels in the strip. The Adafruit_NeoPixel object strip is created with these parameters.

Pin Definitions

Pin numbers are defined for various components:

ultrasonicTrigPin: Trigger pin for the ultrasonic sensor.
ultrasonicEchoPin: Echo pin for the ultrasonic sensor.
buttonPin: Pin for the button.
soundPin: Pin for sound output.
vaporPin: Pin for vapor output.

Enumerated Vase States

This enum defines the possible states of the vase. It includes IDLE, DETECTING, BUTTON_PRESSED, and EMITTING states.

Variable Declarations


Certainly! Let's break down the code into parts and explain each section:

Libraries
cpp
Copy code
#include <Adafruit_NeoPixel.h>
#include <Servo.h>
These lines include two libraries:

Adafruit_NeoPixel.h: This library is used to control NeoPixel LED strips.
Servo.h: This library is used to control servo motors.
NeoPixel Setup
cpp
Copy code
#define NEOPIXEL_PIN 6
#define NEOPIXEL_NUMPIXELS 8

Adafruit_NeoPixel strip = Adafruit_NeoPixel(NEOPIXEL_NUMPIXELS, NEOPIXEL_PIN, NEO_GRB + NEO_KHZ800);
Here, the NeoPixel LED strip is set up. It specifies that the strip is connected to pin 6, and there are 8 pixels in the strip. The Adafruit_NeoPixel object strip is created with these parameters.

Servo Setup
cpp
Copy code
Servo servo;
This line creates a Servo object named servo that will be used to control a servo motor.

Pin Definitions
cpp
Copy code
const int ultrasonicTrigPin = 8;
const int ultrasonicEchoPin = 7;
const int buttonPin = 2;
const int soundPin = 3;
const int vaporPin = 4;
These lines define the pin numbers for various components:

ultrasonicTrigPin: Trigger pin for the ultrasonic sensor.
ultrasonicEchoPin: Echo pin for the ultrasonic sensor.
buttonPin: Pin for the button.
soundPin: Pin for sound output.
vaporPin: Pin for vapor output.

Enumerated Vase States

This enum defines the possible states of the vase. It includes IDLE, DETECTING, BUTTON_PRESSED, and EMITTING states.

Variable Declarations

These lines declare variables:

currentState: Stores the current state of the vase.
stateStartTime: Records the time when the current state started.
buttonPressed: Indicates whether the button is currently pressed.

Setup Function

The setup function is called once when the Arduino starts. It initializes serial communication, sets pin modes for various components, attaches the servo to pin 9, and initializes the NeoPixel strip.

Loop Function

The loop function is called repeatedly. Inside it, there is a switch statement that handles the state machine logic. It checks the current state and performs actions accordingly.

State Machine Logic

This part of the code contains the state machine logic. It checks the current state and performs specific actions based on that state.

## Parts

The device consists of an array of RGB LEDs that can produce over 16 million hues of light. This can catch the attention of the patient keeping him safe from self-damage or any other objects in the room.
![florero vids 5](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/ac5b86ca-ac7c-4a1c-a808-a9225871d386)


It also has two speakers which reproduce music according to the patient's needs to calm and relax. 
![Untitled Project](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/4387c9d1-5fb6-49ac-948d-4bce6aae8054)


Finally, there is a vapor generator that produces certain types of essences to create a uniquely calm atmosphere. 
![florero vids 10](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/d6a91656-fa57-4601-94c1-6b66830a4047)

To initiate the actuators, there is an ultrasonic sensor when someone approaches the device. 

All the actuators and sensors are connected to an Arduino One microcontroller.

First, everything was set up in a cage and tested before the vase model was 3d printed

The first prototype was released:

![Capture1](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/45e4dd8e-5ce7-44e9-9a51-f734dcf41f75)

![Capture2](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/30b2c4fe-3713-4b67-8813-c3fbb09db3d1)


![Capture4](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/ea8fbf51-e5a4-49f9-8621-e3d6aaa2ba10)


## Design and making process of personal snoezelen.

Visual effect: The RGB LEDs positioned on top of the vase, were at an angle that can reflect several colors in a room, and 
they are one of the first things that can catch the attention of anyone. 
These LEDs can stimulate the sense of visuality and make patients more calm with a combination that best fits the patient.

![Capture6](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/df5c13fc-ce51-4a9e-868c-1c282ebd79db)

Sound effect:  Two speakers were used to play Snoezelen music. Mostly, the Snoezelen music was European therapy music. 
So, for Korean patients, traditional folk song-based music is more effective for music therapy.

![Capture7](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/29b555ff-d882-4e54-b43f-1954c5b4d42e)

Smell effect: A vapor generator was used to make smell effects. Various kinds of smells can be applied depending on the patient's needs. 
A multi-diffuser is set to be a future update for the project.

![Capture8](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/25cdf862-b03b-4451-ac12-e21d563e1825)

![Capture9](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/1a2ffccd-c92c-4a09-b0bb-0a862e308623)

The functioning begins with an ultrasonic sensor that once the patient is detected, randomly selects from the three components mentioned before.
The RGB LEDs display unique colors in certain patterns simulating the Snoezelezen chamber's light. 
The speakers play calm sounds related to nature, like wind, waterfall, forest, and ocean. 
Finally, the vapor generator located in a small pool filled with water and essence is ready to produce fragrance with therapeutic properties.




### Presenting the device first to patients

The presentation was with the prototype to the elders to see if the device caught their attention and if they were able to stay near the vase for a long time.
The results were very promising, all of them were attracted especially by the vapor that combined with the other features, kept them reinforcing their senses which is the main gold of the project. Continuous exposure to the device can delay the advance of dementia patients.


![89257500_224959312009289_4832900201637231127_n](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/9187f70c-ced9-4722-b4c8-46d491ecba92)

![Capture5](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/be1c2bfc-bf39-4565-ae11-340a6f04ace2)


![Capture10](https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/9f125338-ecb7-410e-a635-301ed9e16e2e)

Then, all the actuators and the ultrasonic sensor were located inside the vase, which can be shown in the following animation:

https://github.com/kevin343/Personal-Snoezelen-Device/assets/113644566/db0bcc04-1b26-41e2-81d9-3519cb30aad6

## Future upgrades

For future upgrades, a multiple aroma diffuser would be added. Also, the vase is going to be controlled with an app to enhance and supervise the patient. 
Finally, the Arduino UNO is going to be replaced by a more modern microcontroller that has wifi incorporated and a USB type-C input.



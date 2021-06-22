# A turret made with opencv and a raspberry pi. 
This was a project I undertook my Freshman year of High School. The initial goal was to recreate the turrets from the games Portal 1 and Portal 2, however it was shortened to creating a fiber optic christmas tree that uses their voice lines when it detects a person.
## Hardware
The physical components of this project are as follows:
-A raspberry pi zero
-A circuit board for sound-reactive lights.
-A speaker(1 watt, 8 ohms, harvested from an old radio)
-A camera

## The build process
### Setting up opencv on the pi
To set up OpenCV on the Raspberry Pi, the opencv and opencv_contrib repos were cloned from github.
Then, a build folder was made, and cmake was used to create the build files.

While building I kept a fan pointed at the Rasperry Pi to avoid overheating. The build process can take up to 20 hours on the Raspberry Pi Zero. T
For more details see the articles referenced below.

### The sound reactive circuit 
In initial prototypes, the audio signal alone was found to be insufficiant to activate a transistor that was clnnected to
leds. Audio signal seemed to be fluxuating around 0.3 volts, according to a voltmeter. Through use of voltage splitting, 0.5 
volts were added, however it was still unsuccessful. The following circuit found while looking for alternative methods of 
controling leds with sound, and somehow it works(my initial circuit was almost identical however instead of the transistor
switching on a connection to ground it switched on a connection to +5v).
Link to circuit: https://www.instructables.com/topics/Help-with-TIP-31-Sound-Reactive-LEDs/


## Articles referenced:
### A good example of OpenCV on Raspberry Pi
https://github.com/Grayson112233/facerec-door-lock/blob/master/hardware.cpp
### Installation of OpenCV on Raspberry Pi
https://www.alatortsev.com/2018/09/05/installing-opencv-3-4-3-on-raspberry-pi-3-b/
### Increase frame rate
http://answers.opencv.org/question/29957/highguivideocapture-buffer-introducing-lag/
### Facial Detection Docs 
https://docs.opencv.org/3.4.3/d7/d8b/tutorial_py_face_detection.html
### Tracking tutorial for optimization 
https://www.google.com/amp/s/www.learnopencv.com/object-tracking-using-opencv-cpp-python/amp/


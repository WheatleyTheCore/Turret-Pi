# A turret made with opencv and a raspberry pi. 
This started out as a full portal turret, however it has now been shortened to a fiber optic christmas tree that has been given the ability to detect faces and respond verbally in a similar way to the turrets from the game Portal 1 and 2.
## Hardware
The physical components of this project are as follows:
-A raspberry pi zero
-A circuit board that transforms audio into light.
-A speaker(1 watt, 8 ohms, harvester from an old radio)
-Old earbuds, with the two speakers removed and wires exposed)

## The build process
### Setting up opencv on the pi
To set up opencv on the pi, the opencv and opencv_contrib repos were cloned from github.
Then, a build folder was made, and cmake was used to create the build files. It was then built.
While building, keep one or more fans aimed directly at pi until build was finished. The build process is very cpu intensive 
and can take up to 20 hours on the pi zero. The fans will reduce the risk of overheating.
For more details see the articles referenced below.

### The sound reactive circuit 
In initial prototypes, the audio signal alone was found to be insufficiant to activate a transistor that was clnnected to
leds. Audio signal seemed to be fluxuating around 0.3 volts, according to a voltmeter. Through use of voltage splitting, 0.5 
volts were added, however it was still unsuccessful. The following circuit found while looking for alternative methods of 
controling leds with sound, and somehow it works(my initial circuit was almost identical however instead of the transistor
switching on a connection to ground it switched on a connection to +5v).
Link to circuit: https://www.instructables.com/topics/Help-with-TIP-31-Sound-Reactive-LEDs/


## Articles referenced:
### A good example of opencv on pi
https://github.com/Grayson112233/facerec-door-lock/blob/master/hardware.cpp
### Installation of opencv on pi
https://www.alatortsev.com/2018/09/05/installing-opencv-3-4-3-on-raspberry-pi-3-b/
### Increase fr
http://answers.opencv.org/question/29957/highguivideocapture-buffer-introducing-lag/
### Detection docs 
https://docs.opencv.org/3.4.3/d7/d8b/tutorial_py_face_detection.html
### Tracking tutorial for optimization 
https://www.google.com/amp/s/www.learnopencv.com/object-tracking-using-opencv-cpp-python/amp/


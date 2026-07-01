# GO-KART
A go kart design with a embedded rasberry pi and using old FRC parts to power parts of the the drive system.
<img width="787" height="527" alt="Screenshot 2026-06-30 223356" src="https://github.com/user-attachments/assets/72f70169-49ff-4c14-93d4-4ad5a0c53ce9" />

So this is the link to my project's hardware, but if you want to access it and see how I actually made it you will need to make a Onshape account.(srry abt that!) ⬇
https://cad.onshape.com/documents/9b6695b1d4a60c10a7fa9ac2/w/89f098238516000670849f5d/e/6a5bd952239f280b0dcb97d7

This is the link to my github code for the rasberry pi which runs the project.( I did use the help of claude while attempting to code this.)


+ Carries one person in an open cockpit with a seat and a Raspberry Pi heads-up display.
  
+ Uses off-road wheels on a steel chassis that is slightly tapered at both ends.
  
+ Steers with a manual connection to the steering wheel via a ball joint and a steering rack.
  
+ Houses onboard electrical systems including a PDH, Raspberry Pi, Spark Max motor controller, large motor, and a circuit breaker with a fuse for safety reasons.
  
+ Mounting of flat panels in the front and rear for more aerodynamics and overall speed.
  
+ Structural lattice on the sides to have rigidity, but also decrease the weight as much as possible.


Now this project may just look like hardware, but behind the scenes there is a Raspberry Pi controlling everything from the heads-up display to the very motor pushing the go-kart. The way 
the system works is that the motor is connected to the Spark Max, which is essentially just a motor controller. The sparkmax is connected to the power distribution hub with takes power 
from the battery through the circuit breaker. The Raspberry Pi controls the power distribution hub, but sending such a high amount of power to the Raspberry Pi would fry it, so we need to 
use a voltage regulator to lower the power from the PDH from 12V to 5V. Now the final part of the electrical system is the accelerator pedal. The accelerator pedal needs to have an input 
into the Raspberry Pi, but before that, we need an analog-to-digital signal converter to be able to convert the accelerator’s data into the Raspberry Pi. I did this because a go-kart 
controller isvery expensive and I don’t have any funding yet, so I wanted to make this as budget as possible while still keeping it premium.

The code for this is Python with a few extensions because I found that that was best for this scenario. The code for the Raspberry Pi is connected to the Spark Max motor controller via a 
PWM/CAN connection coming out of the Raspberry Pi’s GPIO pins. The Raspberry Pi also has access to an accelerometer and an offline GPS using a UART GPS module with local tile maps. The 
hardware for this project is all aluminum that is ⅛ of an inch thick.  I feel like this is the bets wight to strength ration that should support the wight f the entire thing. The rear wing 
3d printed in chunks, then glued together. While the front panel is aluminum for better weight distribution. I decided upon using 2 sets of disc brakes for my go-kart because it seemed that
the motor would reach a high rpm, resulting in high speed even after I change the gear ratio of the motor to the sprocket.

If you read all of this, thank you for checking out my project!:D

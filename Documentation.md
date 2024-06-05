## Robot Gripper Design

### Assignment Description

This is the design for our project. We will have a claw pick up a can and put it in the trash.
### Evidence
### Top left
![Screenshot 2024-05-31 112944](https://github.com/rkish3721/Robot-Arm/assets/143533539/2fc78cb3-c3b4-4d7b-8184-4ee4718a973d)   
### Back
![image](https://github.com/rkish3721/Robot-Arm/assets/143533539/8f66b934-dc45-4211-ac79-1159919d017c)
### Left
![image](https://github.com/rkish3721/Robot-Arm/assets/143533539/6cd61eda-9c41-4b91-9fdf-fd9f4dd7cdef)









### Part Link 
[https://cvilleschools.onshape.com/documents/52b0cb3af898221881d28299/w/5f7924db806834230dfe3398/e/71406a6a5b6c5dbce54c14c9
]()



### Code
```python
# # SPDX-FileCopyrightText: 2018 Kattni Rembor for Adafruit Industries
#
# SPDX-License-Identifier: MIT

"""CircuitPython Essentials Servo standard servo example"""
import time
import board
import pwmio
from adafruit_motor import servo
from digitalio import DigitalInOut, Direction, Pull


# create a PWMOut object on Pin A2.


pwm1 = pwmio.PWMOut(board.A0, duty_cycle=2 ** 15, frequency=50)
pwm2 = pwmio.PWMOut(board.A1, duty_cycle=2 ** 15, frequency=50)
pwm3 = pwmio.PWMOut(board.A2, duty_cycle=2 ** 15, frequency=50)
# Create a servo object, GripperServo.
GripperServo = servo.Servo(pwm1)
ArmServoA = servo.Servo(pwm2)
ArmServoB = servo.Servo(pwm3)

GripperButton = DigitalInOut(board.D10)
ArmButtonA1 = DigitalInOut(board.D11)
ArmButtonB1 = DigitalInOut(board.D12)

GripperButton.direction = Direction.INPUT
ArmButtonA1.direction = Direction.INPUT
ArmButtonB1.direction = Direction.INPUT

GripperButton.pull = Pull.DOWN
ArmButtonA1.pull = Pull.DOWN
ArmButtonB1.pull = Pull.DOWN

GripperButton2 = DigitalInOut(board.D13)
ArmButtonA2 = DigitalInOut(board.D7)
ArmButtonB2 = DigitalInOut(board.D6)

GripperButton2.direction = Direction.INPUT
ArmButtonA2.direction = Direction.INPUT
ArmButtonB2.direction = Direction.INPUT

GripperButton2.pull = Pull.DOWN
ArmButtonA2 = Pull.DOWN
ArmButtonB2 = Pull.DOWN

CurrentGripperAngle = 90
CurrentArmAAngle = 90 
CurrentArmBAngle = 90 # Initialize the angle
GripperServo.angle=CurrentGripperAngle
ArmServoA.angle=CurrentArmAAngle
ArmServoB.angle=CurrentArmBAngle 

while True:
    if GripperButton.value:  # GripperButton is pressed (remember, we're assuming it's pull-down)
        CurrentGripperAngle = CurrentGripperAngle + 1
        CurrentGripperAngle = max(0, min(180, CurrentGripperAngle))
        GripperServo.angle = CurrentGripperAngle  # Set the new angle
    if GripperButton2.value:  # GripperButton is pressed (remember, we're assuming it's pull-down)
        print(CurrentGripperAngle)
        CurrentGripperAngle = CurrentGripperAngle - 1
        CurrentGripperAngle = max(0, min(180, CurrentGripperAngle))
        GripperServo.angle = CurrentGripperAngle  # Set the new angle
    if ArmButtonA1.value:  # ArmButtonA1 is pressed (remember, we're assuming it's pull-down)
        CurrentArmAAngle = CurrentArmAAngle + 1
        CurrentArmAAngle = max(0, min(180, CurrentArmAAngle))
        ArmServoA.angle = CurrentArmAAngle  # Set the new angle
    if ArmButtonA2.value:  # ArmButtonA1 is pressed (remember, we're assuming it's pull-down)
        print(CurrentArmAAngle)
        CurrentArmAAngle = CurrentArmAAngle - 1
        CurrentArmAAngle = max(0, min(180, CurrentArmAAngle))
        ArmServoA.angle = CurrentArmAAngle  # Set the new angle
    if ArmButtonB1.value:  # ArmButtonA1 is pressed (remember, we're assuming it's pull-down)
        CurrentArmBAngle = CurrentArmBAngle + 1
        CurrentArmBAngle = max(0, min(180, CurrentArmBAngle))
        ArmServoB.angle = CurrentArmBAngle  # Set the new angle
    if ArmButtonB2.value:  # ArmButtonA1 is pressed (remember, we're assuming it's pull-down)
        print(CurrentArmBAngle)
        CurrentArmBAngle = CurrentArmBAngle - 1
        CurrentArmBAngle = max(0, min(180, CurrentArmBAngle))
        ArmServoB.angle = CurrentArmBAngle  # Set the new angle
    time.sleep(0.01)  # Small delay to avoid excessive checking
```
### Wiring
![image](https://github.com/rkish3721/Robot-Arm/assets/143533512/517dab42-1290-40be-af97-fea0422d426a)

### Process and Schedule
Ryan and I took a while to start this project but we have worked diligently for the last month and a half. We have completed our Onshape and we worked on the code and wiring over the weekend. We also changed seats which is a sacrifice we were willing to make to lock in on our project. We started with the Onshape which took a while and then we did the wiring and code over the last weekend of May. 

### Discussion of Problems
One problem we experienced was getting the gears to align. We needed the right size for the spikes and the right amount of spikes. Another problem we experienced was getting the size right for the many pieces and getting them all to align together and move fluidly. We also struggled a little with the code and having each motor controlled by a button.

### Nuggets of Wisdom
Some nuggets of wisdom that we acquired on this project were time management using different tools on Onshape. Our time management at the beginning of the project was atrocious and we took a while to start. We then figured out how to accurately manage our time and we made good headway on the project. We also learned how to use the coincident tool while making our final arm piece. My advice to the reader that would lead to a better project than ours would be to start on time and use your time wisely. Time is money in this project and if you don't use your time well you won't succeed. 

### Reflection
This assignment was a tough final assignment where we didn't lock in in the beginning so we had a lot of work to do at the end. We struggled with starting the Onshape and working on the different arm pieces. We also needed to get the right amount of teeth on the gears. Ryan did the code and did very well and we did the onshape together. The code was a simple control of multiple servo motors using buttons.

### Obituary
The death of our project is deeply saddening to us. The main failure for us during this project was our time management. We didn't use our time well at the beginning of this project which led to the death of the project. We tried to make a comeback in the month of May but fell just short. If we were to continue to be able to work on this project we would have used our time better so we would be able to print more than once. This would increase our chances of success on the project and we are deeply crushed that we failed to use our time well.


# Design Goal
Our design will aim to pick up cans on a desk and crush them into discs which can be placed in a trash can. It will do this with a arm head that can both pick up the cans and smash them, while moving to the trash can. It will be operated mostly by DC motors. The arm head will have rubber tips to help with grip and the can smasher will sit perpenducular to the grabbers. They will move along a rail that is controlled by a servo. Once smashed, the grabbers will release and the can will be dropped into the trash can. It will identify a can by looking for a specific color of soda with a color sensor. 
# Schedule
CAD Design - April 15  
Printing and assembly - April 29  
Coding/reprinting to fix bugs - May 17  
Testing/ polishing - May 25  
More testing and bug fixing - June 1  
Due - End of school  
# Design
![IMG_4321](https://github.com/rkish3721/Robot-Arm/assets/143533512/43ed9875-583b-4a61-a532-75eb30a5c455)
# Pseudocode
Scan for mtn dew color  
move to above it   
rotate to right orientation  
move head down  
grab it  
move to trash can    
crush it  
drop it  
return to starting position   
# Materials
3 Servos  
1 Dc Motor  
Ceramic for arm parts  
4 Stick on rubber things  
PLA printed gears for base  
PLA printed head  
extra weight for base  
# Risk Midigation
The risks of this project include: injury of hitting someone, grabbing something that isn't supposed to be, grabbing someone wearing a neon shirt, and missing the trash can. To combat these we will: Make the arm move slowly to avoid injury, limit scanning area to only the desk, add a failsafe button that the person can press to stop the arm, and hardcode the trash can to the same spot so it cannot miss. 

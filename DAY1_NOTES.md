Inputs:
road_list: the list to modify.
sign: the sign to insert.
position: where the new sign should be inserted.
Return:
False if the position is invalid.
True after successfully inserting the sign.
Valid position range:
text
0 through len(road_list)
The position equal to len(road_list) is valid because it means inserting at the end of the list.
Important insight: ins# Obersving the road_similation.py from day one, I noticed the following
*The are ten function or tasks I have to complete.
is_valid_sign
#Input:
sign: the value to check.
#Return:
True if the sign is valid.
False otherwise.
#Rules to remember:
The sign must be text.
"bus" is valid.
"zebra" is valid.
Numeric text from "20" through "100" is valid.
Other values are invalid.
#This function is a validation function. Its job is to answer a yes-or-no question.
===============================================================
get_sign_type
#Input:
sign: one road-list item.
#Return:
One of these text values:
"bus"
"zebra"
"speed"
"road"
#Rules to remember:
"bus" should be classified as "bus".
"zebra" should be classified as "zebra".
A numeric speed sign should be classified as "speed".
Anything else should be classified as "road".
#This function classifies a value. It does not change the road list.
=============================================================

get_speed_limit
#Inputs:
sign: the current road item.
current_limit: the speed limit currently being used.
#Return:
The sign’s number as an integer if the sign is a speed sign.
current_limit if the sign is not a speed sign.
For example:
"80"       → 80
"zebra"    → current_limit
"bus"      → current_limit
"road"     → current_limit
#Important insight: speed signs are stored as text, but the returned speed limit should be an integer.
==================================================================
get_target_speed
#Inputs:
limit: the current speed limit.
#stop_timer: the remaining stopping time at a zebra crossing.
Return:
0 when stop_timer is greater than 0.
limit when stop_timer is 0 or no longer active.
#This function determines the speed the car should aim for. It does not directly change the car’s current speed.
============================================================

adjust_speed

#Inputs:
speed: the car’s current speed.
target: the speed the car should reach.
#Return:
The car’s next speed after one adjustment step.
#Rules:
If the current speed is below the target, add ACCELERATION, which is 5.
If the current speed is above the target, subtract BRAKING, which is 20.
If the adjustment would go beyond the target, return the target instead.
If the current speed already equals the target, keep it unchanged.
#Important insight: this function changes speed gradually. It should not immediately jump from the current speed directly to the target.
==================================================================
count_signs

#Input:
road_list: a list containing road items.
#Return:
A tuple containing three values in this exact order:
(speed_signs, zebras, buses)
The function must use a loop to count:
#Numeric speed signs.
"zebra" entries.
"bus" entries.
#Important insight: the return order matters. Even if the counts are correct, returning them in the wrong order would cause problems elsewhere in the program.

=============================================================

ask_for_number
#Inputs:
question: the message shown to the user.
low: the smallest allowed number.
high: the largest allowed number.
#Return:
A valid whole number as an integer.
#Rules:
Keep asking until the user enters a valid number.
Use try/except because the user may type text that cannot be converted to an integer.
Reject numbers below low.
Reject numbers above high.
#Important insight: this function combines user input, conversion, validation, and repetition.
===============================================================

insert_sign
#Inputs:
road_list: the list to modify.
sign: the sign to insert.
position: where the new sign should be inserted.
#Return:
False if the position is invalid.
True after successfully inserting the sign.
Valid position range:
0 through len(road_list)
The position equal to len(road_list) is valid because it means inserting at the end of the list.
#Important insight: insertion increases the length of the road list.
=================================================================
replace_sign

#Inputs:
road_list: the list to modify.
sign: the replacement sign.
index: the existing item to replace.
#Return:
False if the index is invalid.
True after successfully replacing the sign.
Valid index range:
0 through len(road_list) - 1
Unlike insertion, len(road_list) is not a valid replacement index because it is one position past the final item.
#Important insight: replacement keeps the road list the same length.
=================================================================
get_journey_summary

#Input:
road_list: the complete journey list.
#Return:
Four values in this exact order:
Python
(signs_passed, length_m, START_NAME, END_NAME)
#Rules:
Count every item that is not "road" as a sign passed.
Calculate the road length by multiplying the number of segments by SEGMENT_M.
Use the constants START_NAME and END_NAME.
Use a loop to count the signs.
Important insight: the journey length is based on all road segments, not only the signs.

insert_sign
#Inputs:
road_list: the list to modify.
sign: the sign to insert.
position: where the new sign should be inserted.
#Return:
False if the position is invalid.
True after successfully inserting the sign.
#Valid position range:
text
0 through len(road_list)
The position equal to len(road_list) is valid because it means inserting at the end of the list.
Important insight: ins


### Someinthing I am not understanding well, is the idea of the use of return, how to know you need one, and hwo ti works.

SFD Lab 1 — Kigali Roads

This project is a Python simulation of a car travelling from ALU Rwanda to the Convention Center in Kigali.

I worked through the TODO functions in road_simulation.py and learned how each function affects the simulation. The road is stored as a list. Each item in the list represents one 100-metre road segment.

Files

The project uses these files:

•
road_simulation.py — the file where I completed the TODO functions.

•
transit_program.py — runs the menus and the driving program. I did not edit it.

•
engine.py — supports the web display. I did not edit it.

•
index.html — displays the simulation. I did not edit it.

What I learned while working on the project

I learned that signs are stored as text. For example, "80" is different from 80. The first one is a string and the second one is an integer.

I used isinstance(sign, str) to check the type of a sign. I also learned how not reverses a Boolean result. For example, not isinstance(sign, str) means that the value is not text.

I used try and except ValueError when converting text into an integer. This prevents the program from crashing when a value such as "hello" cannot be converted into a number.

I learned that while True is useful when the program needs to keep asking until the user gives a valid answer. The continue statement skips the failed attempt and starts the next one, while return ends the function when the answer is valid.

I also learned how a for loop can go through a list and use counters to count different types of signs. The loop does the counting, but the function returns the final tuple.

Completed functions

is_valid_sign(sign)

Checks whether a sign is valid. A valid sign must be text and must be either:

•
"bus"

•
"zebra"

•
A number from 20 to 100 written as text, such as "60" or "80"

It returns True or False.

get_sign_type(sign)

Classifies one road item as:

•
"bus"

•
"zebra"

•
"speed"

•
"road"

It returns "road" for an ordinary road item or an unrecognized value.

get_speed_limit(sign, current_limit)

Changes the current speed limit only when the sign is a speed sign. A value such as "80" is converted to the integer 80. Other signs leave the current limit unchanged.

get_target_speed(limit, stop_timer)

Returns 0 while the car is still waiting at a zebra crossing. When the timer reaches 0, it returns the current speed limit.

adjust_speed(speed, target)

Moves the current speed one step toward the target. The car accelerates by 5 and brakes by 20. It does not go past the target.

count_signs(road_list)

Uses a loop to count speed signs, zebra crossings, and buses. It returns the counts in this order:

Python


(speed_signs, zebras, buses)



Ordinary "road" items are ignored because this function only counts the three special types.

ask_for_number(question, low, high)

Asks the user for a whole number and keeps asking until the answer is within the required range. It handles text that cannot be converted to an integer with try and except.

insert_sign(road_list, sign, position)

Adds a valid sign to the road list. The position can be from 0 through len(road_list), so inserting at the end is allowed. It returns True when the insertion works and False when it does not.

replace_sign(road_list, sign, index)

Replaces a sign at an existing index. The index must be from 0 through len(road_list) - 1. It returns True after a successful replacement and False for an invalid sign or index.

get_journey_summary(road_list)

Counts the signs passed, calculates the length of the road, and returns:

Python


(signs_passed, length_m, START_NAME, END_NAME)



Every item that is not "road" counts as a sign passed. The road length is the number of segments multiplied by SEGMENT_M.

Running the program

From the project folder, run:

Bash


python3 road_simulation.py



To check the file for syntax errors, run:

Bash


python3 -m py_compile road_simulation.py



Testing before committing

I check the changes before committing with:

Bash


git diff -- road_simulation.py
git status



The protected files should not be changed. A useful commit message for the completed functions is:

Bash


git add road_simulation.py README.md
git commit -m "feat: complete Kigali road simulation"




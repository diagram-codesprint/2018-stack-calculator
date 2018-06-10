# Stack Calculator

The idea of this project is to create a flexible workflow that allows a student with limited vision and limited motor coordination to succeed in school.

To make the problem tractable, we focused on one math problem for this sprint.

This idea is to provide programming-like tools to the student, who can use them to create lists of numbers to use as a scratchpad.

This is intended to be a voice interface, but may include physical buttons as needed. Our feeling is that physical buttons will be most useful for:
1. Initiating a voice command
2. Rejecting a voice recognition result
3. Confirming a recognition result.

Commands used in the dialog below are:
1. Start (name): Start a new named list, and make it the output list
2. Insert: Add an item to the current output list
3. YES: Confirm a voice recognition result
4. NO: Reject a voice recognition result
5. Read (name): Read the named list, or the current input list if no name specified
5. Iterate (name): Read the named list, or the current input list if no name specified. After each item, listen for an item to be added to the current output list.
6. Done: Complete the current step, and make the output list(s) input

Other commands that are like needed include:
1. Repeat: Repeat last utterance
2. Start (name): Go to the start of the input list and read the first item (this collides with start above - need to rename one of them)
3. Next: Go to the next item of the current input list

We also need some affordance to look at the overall problem - to see the starting list and the intermediate lists, both for a teacher to "check the work" and for the student to review if they get distracted and lose track of where they are.

## Example dialog
The dialog below is an example of adding three two-digit numbers. The user's input is right-aligned, and the system's responses are left-aligned.

Input list called ‘start’

52, 49, 32

<p align="right"> <b>Start</b> tens
  
Inserting to new list ‘tens’

<p align="right"> <b>Iterate</b>

52

<p align="right">50

Inserted 50

<p align="right"><b>YES</b>

49

<p align="right">40

Inserted 60

<p align="right"><b>NO</b>

Trying again. 49

<p align="right">40

Inserted 40

<p align="right"><b>YES</b>

32

<p align="right">30

Inserted 30

<p align="right"><b>YES</b>

BING - End of list

<p align="right"><b>Start</b> ones

Inserting to new list ones

<p align="right"><b>Iterate</b>

52

<p align="right">2

Inserted 2

<p align="right"><b>YES</b>

49

<p align="right">9

Inserted 9

<p align="right"><b>YES</b>

32

<p align="right">2

Inserted 2

<p align="right"><b>YES</b>

BING
  
<p align="right"><b>Done</b>

Two lists of numbers

Input list ‘tens’ with 50, 40, 30

Input list ‘ones’ with 2, 9, 2

<p align="right"><b>Read</b> tens

List with tens is: 50, 40, 30

<p align="right"><b>Insert</b> 120

Inserted 120

<p align="right"><b>Read</b> ones

List with ones is: 2, 9, 2

<p align="right"><b>Insert</b> 13

Inserted 13

<p align="right"><b>Done</b>

List of numbers 120, 13

<p align="right"><b>Insert</b> 133

Inserted 133

<p align="right"><b>Done</b>

List of numbers 133

<p align="right"><b>Done</b>

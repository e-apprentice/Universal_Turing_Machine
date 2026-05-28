# Physical Implementation of a Universal Turing Machine

This project presents a physical implementation of a Universal Turing Machine (UTM) using low-cost embedded systems and electromechanical components. Unlike software simulations, this system demonstrates computation at a hardware level using a memory tape, read/write mechanisms, and a microcontroller-based control unit.

The system processes input encoded via punched cards and executes state transitions defined by a transition table, simulating the theoretical model of a Universal Turing Machine in real-world hardware.

## Technologies Used

Arduino IDE / Embedded C++
ESP32-CAM
Stepper Motor Control
Basic Image Processing
Digital logic and finite state machine design

## The concept behind the program

Assume the following string:
0 F R 0 F L 0
The parser interprets it as:

- 0 -> state identifier(completely useless now if I'm being completely honest)
- F R 0 -> executed if the head reads 0 from the tape
  - F -> flip the bit from 0 to 1
  - R -> move the head right
  - 0 -> transition to state 0
- F L 0 -> executed if the head reads 1 from the tape
  - F -> flip the bit from 1 to 0
  - L -> move the head left
  - 0 -> transition to state 0

The execution is assume in this order of tape operation, head operation, state transition. The programmer is expected to write their programs in this manner.
Other symbols not used here are:

- N(tape opeartion) -> no operation/don't flip the bit
- S(head operation) -> stay/don't move the head
- H(state transition) -> halt the program

Save the program as a .turing file and run it using the interpreter. Instruction below.

## Compile

Compilation is done with cmake

## Run

```
bin/tlang programs/loop.turing
```

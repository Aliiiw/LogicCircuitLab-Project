# LogicCircuitLab-Project
Calculator, Clock, Name

1. Calculator
In CPUs, there is a specific component for computation called “Arithmetic Logic Unit” (abbreviated
to ALU). You are asked to implement a simple ALU which performs the four common operations
(Add, Subtract, Multiply, Divide).
The component takes two 4-bit number, and a 2-bit number for mode which identifies the desired
operation. Suppose all numbers are in the 2’s complement form, except for “divide” operation. For
“divide” operation, suppose the numbers are unsigned.
The component outputs an 8-bit number as the result of the operation. If the operation was “divide”,
the first four bits show the multiplicand and the last four bits show the remainder.
The component also outputs four flags.

2. Clock
Design a clock using 6 seven-segments. Note that you can set your clock using binary inputs for hour,
minute and second. For example, if you set the input of your hour part as 10010 and then run your
design, hour should start at 18 and then continue counting.

3. Name block
Through use of different kinds of segments, you should design a block which will represent your name.
At first all of the segments are off and after 5 seconds the first letter of your name is shown. This
sequence continues until all of the letters are on, then you name will blink until end of the day.

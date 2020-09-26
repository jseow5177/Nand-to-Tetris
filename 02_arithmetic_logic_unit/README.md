# Boolean Arithmetic and Arithmetic Logic Unit (ALU)

The ALU is the centerpiece chip that executes all the arithmetic and logical operations performed by the computer. Typically, an ALU computes a function on two inputs and outputs the result. The function is one out of a family of pre-defined operations. The example of operations that can be performed are as follows:

- Arithmetic operations: integer addition, multiplication, division ...
- Logical operations: And, Or, Xor, ...

In this project, a minimal ALU named as the Hack ALU is used. It operates on two 16-bit inputs and gives a 16-bit output. It computes one out of a family of 18 core functions. It decides on which function to operate based on six 1-bit inputs known as control bits. Note that with the 6 bits, the ALU can actually compute up to 64 functions in total.

Below shows the specification and truth table of our Hack ALU with the 18 functions:

![alu-specs](./img_assets/alu-specs.png)

![alu-table](./img_assets/alu-table.png)

Note that the control bits are applied on the inputs in the sequence of zx, nx, zy, ny, f and no. The additional two outputs, zr and ng will be used in the later units of this project.

## Adders
Adders are chips used to perform addition on numbers. We can also compute negative numbers easily with adders, which then allow us to perform subtraction.

### 1. Half Adder
Designed to add two bits.

![half-adder](./img_assets/half-adder.png)

### 2. Full Adder
Designed to add three bits.

![full-adder](./img_assets/full-adder.png)

### 3. Add16
A 16-bit adder that handles the addition of two 16-bit binary numbers. It is constructed using the Half Adder and Full Adder designed above. Note that the adder in this project does not detect or handle overflow.

The 16-bit adder used here is a ripple-carry adder. It is same as the pencil-and-paper methods of addition where we start at the rightmost digit position and add the digits until the leftmost position. The addition on the left is dependent on the right because it needs to take into account the possibility of having to add an extra 1 from a carry. For example, 9 + 5 = 4, carry 1. Hence, the left additions cannot be carried out until the right additions are completed.

The ripple-carry adder is inefficient when the number of bits, n is large as the signal needs to traverse through long distance from right to left. To solve this problem, there is another type of adder known as carry-lookahead adder.

![add-16](./img_assets/add-16.png)

### 4. Inc16
A special-purpose adder that adds a constant 1 to a given number.

## Final Remarks
Note that multiplication and division operation are not handled in our Hack ALU. They will be dealt in the later units of this project.

## References
1. [The Elements of Computing Systems, Chapter 2](https://b1391bd6-da3d-477d-8c01-38cdf774495a.filesusr.com/ugd/44046b_89c60703ebfc4bf39acef13bdc050f5d.pdf)
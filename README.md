# 4-BIT-RIPPLE-COUNTER
Developed by; yogesh D 
Reg no; 24006488
**AIM:**

To implement  4 Bit Ripple Counter using verilog and validating their functionality using their functional tables

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 Bit Ripple Counter**

A binary ripple counter consists of a series connection of complementing flip-flops (T or JK type), with the output of each flip-flop connected to the Clock Pulse input of the next higher-order flip-flop. The flip-flop holding the least significant bit receives the incoming count pulses. The diagram of a 4-bit binary ripple counter is shown in Fig. below.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/cb4b74d4-31ab-4359-95d0-d22e67daba13)

In timing diagram Q0 is changing as soon as the negative edge of clock pulse is encountered, Q1 is changing when negative edge of Q0 is encountered(because Q0 is like clock pulse for second flip flop) and so on.

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/a573a7d6-014e-4e54-93e6-e2ac9530960b)

![image](https://github.com/naavaneetha/4-BIT-RIPPLE-COUNTER/assets/154305477/85e1958a-2fc1-49bb-9a9f-d58ccbf3663c)

**Procedure**
/* 1.Write the Verilog code in Quartus Prime for the 4-bit ripple counter.
2.Compile and run the program to ensure it is error-free.
3.Generate the RTL schematic to visualize the flip-flop connections.
4.Create nodes for the clock input (CLK) and counter outputs (Q0, Q1, Q2, Q3).
5.Simulate the design for multiple clock cycles to observe the ripple effect.
6.Verify the timing diagrams to ensure the counter toggles through all states (0000 to
1111).
7.Save the RTL schematic and timing diagrams for documentation and validation. */

**PROGRAM**

/* Program for 4 Bit Ripple Counter and verify its truth table in quartus using Verilog programming.
module ripple(
input wire clk, // Clock input
output reg [3:0] count // 4-bit counter output
);
// Counter logic
always @(posedge clk) begin
if (count == 4'b1111) // Reset when count reaches 15
count <= 4'b0000;
else
count <= count + 1; // Increment count
end
endmodule
// Testbench
module RippleCounter_tb;
// Inputs
reg clk;
// Outputs
wire [3:0] count;
// Instantiate the counter
RippleCounter uut(
.clk(clk),
.count(count)
);
// Clock generation
initial begin
clk = 0;
forever #5 clk = ~clk; // Toggle clock every 5 time units
end
RTL LOGIC FOR 4 Bit Ripple Counter
TIMING DIGRAMS FOR 4 Bit Ripple Counter
// Stimulus
initial begin
// Wait for a few clock cycles
#10;
// Display header
$display("Time | Count");
$display("-----------------");
// Functional table testing
// Increment count 16 times and display the count
repeat (16) begin
#5; // Wait for one clock cycle
$display("%4d | %b", $time, count);
end
// End simulation
$finish;
end
endmodule

 Developed by:Yogesh D  RegisterNumber: 24006488
*/

**RTL LOGIC FOR 4 Bit Ripple Counter**
![Screenshot 2024-12-24 101902](https://github.com/user-attachments/assets/ec6cfccc-9947-4a9a-8f73-88cd032df5dc)

**TIMING DIGRAMS FOR 4 Bit Ripple Counter**
![Screenshot 2024-12-24 101912](https://github.com/user-attachments/assets/469dd393-516e-4512-aada-20804713de68)

**Truth Taable:
![Screenshot 2024-12-24 102123](https://github.com/user-attachments/assets/8510fb3d-14cb-4139-88eb-443700e7f140)

**RESULTS**
Thus, the 4-bit Ripple Counter was successfully implemented, and its functionality was
validated using the truth table.

## Aim
To design and simulate a seven-segment display driver using Verilog HDL, and verify its functionality through a testbench in the Vivado 2023.1 environment. The objective is to implement the logic that converts a 4-bit binary input into the corresponding 7-segment display output for the digits 0 to 9.

## Apparatus Required
Vivado 2023.1
Computer system with a suitable operating system.

## Procedure

Launch Vivado 2023.1:

Open Vivado and create a new project.
Design the Verilog Code:

Write the Verilog code for the seven-segment display, defining the logic that maps a 4-bit binary input to the corresponding segments (a to g) of the display.
Create the Testbench:

Write a testbench to simulate the seven-segment display behavior. The testbench should apply various 4-bit input values and monitor the corresponding output on the seven-segment display.
Add the Verilog Files:

Add both the design module and the testbench in the Vivado project.
Run Simulation:

Run the behavioral simulation to verify the output. Ensure the seven-segment display behaves correctly for binary inputs 0000 to 1001 (decimal 0 to 9).
Observe the Waveforms:

Analyze the output waveforms in the simulation window, and verify that the correct segments light up for each digit.
Save and Document Results:

Capture screenshots of the waveform and save the simulation logs. These will be included in the lab report.

Diagram
![image](https://github.com/user-attachments/assets/d7ecb419-906e-4e3b-9b82-f86ced4f364a)


## Verilog Code for Seven-Segment Display

// seven_segment_display.v
module sevensegment(bcd,seg);

input[3:0]bcd;

output reg[6:0]seg;

always @(bcd)

case(bcd)

0:seg=7'b0000001;

1:seg=7'b1001111;

2:seg=7'b0010010;

3:seg=7'b0000110;

4:seg=7'b1001100;

5:seg=7'b0100100;

6:seg=7'b0100000;

7:seg=7'b0001111;

8:seg=7'b0000000;

9:seg=7'b0000100;

default:seg=7'b1111111;

endcase

endmodule

## output

![Screenshot (28)](https://github.com/user-attachments/assets/b34a5012-4486-4092-8dbf-67ec3fa3a277)


## Testbench for Seven-Segment Display:

module sevenseg(seg,s); 
input [3:0]seg; 
output reg[6:0]s; 
always@(seg) 
begin 
    case(seg) 
        4'd0 : s= 7'b0111111; 
        4'd1 : s= 7'b0000110; 
        4'd2 : s= 7'b1011011; 
        4'd3 : s= 7'b1001111; 
        4'd4 : s= 7'b1100110; 
        4'd5 : s= 7'b1101101; 
        4'd6 : s= 7'b1111101; 
        4'd7 : s= 7'b0000111; 
        4'd8 : s= 7'b1111111; 
        4'd9 : s= 7'b1100111; 
        default:s=7'b0000000; 
    endcase
end
endmodule

## output 

![Screenshot (29)](https://github.com/user-attachments/assets/60e756ab-8289-431e-aa8c-12af3ff34bc0)

       

   
## Conclusion
In this experiment, a seven-segment display driver was successfully designed and simulated using Verilog HDL. The simulation results confirmed that the display correctly represented the digits 0 to 9 based on the 4-bit binary input. The testbench effectively verified the functionality of the seven-segment display by applying various input combinations and observing the corresponding segment outputs. This experiment highlights how Verilog HDL can be used to control hardware components like a seven-segment display in digital systems.

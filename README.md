# Verilog-Code-for-Swapping-Three-Numbers
Aim
To design and simulate a Verilog HDL code for swapping the values of three numbers without using any temporary variables, and verify the correctness of the swapping operation through a testbench using the Vivado 2023.1 simulation environment.

Apparatus Required
Vivado 2023.1 or equivalent Verilog simulation tool.

Procedure
Launch Vivado 2023.1:

Open Vivado and create a new project.
Write the Verilog Code for Swapping:

Write the Verilog code that swaps the values of three numbers (a, b, and c) using basic arithmetic or bitwise operations without using temporary variables.
Create the Testbench:

Write a testbench to simulate the swapping operation. The testbench should initialize three numbers, trigger the swapping module, and check if the values are swapped correctly.
Add the Verilog Files:

Add the Verilog module and the testbench file to the Vivado project.
Run Simulation:

Run the behavioral simulation in Vivado to verify the swapping operation.
Observe the Waveforms:

Examine the waveform to confirm that the values of the three numbers are swapped as expected.
Save and Document Results:

Capture the waveform output and include the results in your report for verification.

Verilog Code:

module swap_three_numbers(
    input wire [7:0] a_in,b_in,c_in,  // 8-bit inputs 
    output reg [7:0] a_out,b_out,c_out); //8-bit outputs
    always @(*) begin
        a_out = b_in;  //assign a_out as b_in
        b_out = c_in;  //assign b_out as c_in
        c_out = a_in;  //assign c_out as a_in 
    end
endmodule

OUTPUT : ![swapping of three numbers](https://github.com/user-attachments/assets/c5fda805-0e0d-4d2d-949e-bd0b38add441)


Testbench for Swapping Three Numbers:

`timescale 1ns / 1ps
module swap_three_numbers_tb;

    // Inputs
    reg [7:0] a;
    reg [7:0] b;
    reg [7:0] c;

    // Outputs
    wire [7:0] a_out;
    wire [7:0] b_out;
    wire [7:0] c_out;

    // Instantiate the Unit Under Test (UUT)
    swap_three_numbers uut (
        .a_in(a),
        .b_in(b),
        .c_in(c),
        .a_out(a_out),
        .b_out(b_out),
        .c_out(c_out)
    );

    // Test procedure
    initial begin
        // Initialize inputs with hexadecimal values
        a = 8'h0C; // Assign hex 0C to a (12 in decimal)
        b = 8'h0E; // Assign hex 0E to b (14 in decimal)
        c = 8'h10; // Assign hex 10 to c (16 in decimal)

        // Wait for 10 ns to observe swap
        #10;

        // Display the original values
        $display("Before Swap: a = %h, b = %h, c = %h", a, b, c);
        #10;

        // Display the swapped output values
        $display("After Swap: a = %h, b = %h, c = %h", a_out, b_out, c_out);
        
        // Stop the simulation
        #10 $stop;
    end
endmodule
    

Conclusion
In this experiment, a Verilog HDL code for swapping three numbers was designed and successfully simulated. The testbench verified the swapping operation, showing that the values of three input numbers (a, b, and c) were swapped correctly without the use of temporary variables. This experiment demonstrated the effectiveness of Verilog in implementing logical operations and control mechanisms such as swapping values. The simulation results confirm the correct functionality of the design.

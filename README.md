![Screenshot 2024-03-20 222815](https://github.com/Christina1106/VLSI-LAB-EXP-1/assets/161043650/2980eb82-3dc0-4516-ad8d-055f5acb3e12)# VLSI-LAB-EXPERIMENTS
AIM: To simulate and synthesis Logic Gates,Adders and Subtractor using Xilinx ISE.

APPARATUS REQUIRED: Xilinx 14.7 Spartan6 FPGA

PROCEDURE: STEP:1 Start the Xilinx navigator, Select and Name the New project. STEP:2 Select the device family, device, package and speed. STEP:3 Select new source in the New Project and select Verilog Module as the Source type. STEP:4 Type the File Name and Click Next and then finish button. Type the code and save it. STEP:5 Select the Behavioral Simulation in the Source Window and click the check syntax. STEP:6 Click the simulation to simulate the program and give the inputs and verify the outputs as per the truth table. STEP:7 Select the Implementation in the Sources Window and select the required file in the Processes Window. STEP:8 Select Check Syntax from the Synthesize XST Process. Double Click in the Floorplan Area/IO/Logic-Post Synthesis process in the User Constraints process group. UCF(User constraint File) is obtained. STEP:9 In the Design Object List Window, enter the pin location for each pin in the Loc column Select save from the File menu. STEP:10 Double click on the Implement Design and double click on the Generate Programming File to create a bitstream of the design.(.v) file is converted into .bit file here. STEP:12 Load the Bit file into the SPARTAN 6 FPGA STEP:11 On the board, by giving required input, the LEDs starts to glow light, indicating the output.

Logic Diagram :

Logic Gates:
![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/ee17970c-3ac9-4603-881b-88e2825f41a4)


Half Adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/0e1ecb96-0c25-4556-832b-aeeedfdfe7b9)


Full adder:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/9bb3964c-438f-469d-a3de-c1cca6f323fb)


Half Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/731470b7-eb4e-49f8-8bb7-2994052a7184)



Full Subtractor:

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/d66f874b-c1f2-44b3-a035-7149b56430c1)



8 Bit Ripple Carry Adder

![image](https://github.com/navaneethans/VLSI-LAB-EXPERIMENTS/assets/6987778/7385a408-40a5-4203-8050-b72818622d79)



VERILOG CODE:
Half Adder:
program halfadder dataflow

//half adder using Dataflow modeling
module half_adder(a,b,sum, carry);
input a,b;
output sum, carry; // sum and carry
assign sum = a^b;
assign carry = a&b;
endmodule

output:
![Screenshot 2024-03-20 221138](https://github.com/Christina1106/VLSI-LAB-EXP-1/assets/161043650/f6dac197-af98-4c7f-a938-54e515530eb3)
![Screenshot 2024-03-19 003112](https://github.com/Christina1106/VLSI-LAB-EXP-1/assets/161043650/bffa8c5b-009c-4f43-87a0-3d4207656bbf)

Half Subtractor:
program for half subtractor dataflow

module half_subtractor(D,Bo,A,B);
input A,B;
output D,Bo;
assign D = A^B;
assign Bo = (~A)&B;
endmodule

output:
![Screenshot 2024-03-20 222643](https://github.com/Christina1106/VLSI-LAB-EXP-1/assets/161043650/eac5b70c-8eff-4384-b076-65525288cadd)
![Screenshot 2024-03-20 222815](https://github.com/Christina1106/VLSI-LAB-EXP-1/assets/161043650/7b6cdef1-072d-4fc2-9942-4b47d4e872fc)


Full Adder:
program for full adder gatelevel

//full adder using Gatelevel modeling
module fulladder (sum, cout, a,b,c);
input a,b,c;
output sum,cout;
wire w1,w2,w3,w4,w5;
xor x1 (w1,a,b);
xor x2(sum,w1,c); 
and a1 (w2,a,b); 
and a2(w3,b,c);
and a3(w4,a,c);
or o1 (w5,w2,w3); 
or o2(cout, w5,w4);
endmodule

output:
![Screenshot 2024-03-17 224831](https://github.com/Christina1106/VLSI-LAB-EXP-1/assets/161043650/bf065cc6-5b8f-4b94-9ad7-d80b7bdd85f4)
![Screenshot 2024-03-17 225003](https://github.com/Christina1106/VLSI-LAB-EXP-1/assets/161043650/ab7f39f4-942a-4595-82ad-2c730dac6580)

Full Subtractor:
program for Full Subtractor dataflow

module full_subtractor(a, b, c,D, Bout);
input a, b, c;
output D, Bout;
assign D = a^b^c;
assign Bout = (a & b) | ((a^b) & c);
endmodule

Output:
![Screenshot 2024-03-25 011831](https://github.com/Christina1106/VLSI-LAB-EXP-1/assets/161043650/9b6b5c44-0fe5-4646-b541-7f7baf212b85)
![Screenshot 2024-03-25 011933](https://github.com/Christina1106/VLSI-LAB-EXP-1/assets/161043650/7e942122-7332-4cba-9eff-af24eb57f4d9)



OUTPUT:

-----Place a Waveform Generated from Xilinx ISE

RESULT:


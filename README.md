### SYNCHRONOUS-UP-COUNTER

**AIM:**

To implement 4 bit synchronous up counter and validate functionality.

**SOFTWARE REQUIRED:**

Quartus prime

**THEORY**

**4 bit synchronous UP Counter**

If we enable each J-K flip-flop to toggle based on whether or not all preceding flip-flop outputs (Q) are “high,” we can obtain the same counting sequence as the asynchronous circuit without the ripple effect, since each flip-flop in this circuit will be clocked at exactly the same time:

![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/d5db3fa0-e413-404c-b80e-b2f39d82e7e8)


![image](https://github.com/naavaneetha/SYNCHRONOUS-UP-COUNTER/assets/154305477/52cb61eb-d04b-442d-810c-31185a68410b)

Each flip-flop in this circuit will be clocked at exactly the same time.
The result is a four-bit synchronous “up” counter. Each of the higher-order flip-flops are made ready to toggle (both J and K inputs “high”) if the Q outputs of all previous flip-flops are “high.”
Otherwise, the J and K inputs for that flip-flop will both be “low,” placing it into the “latch” mode where it will maintain its present output state at the next clock pulse.
Since the first (LSB) flip-flop needs to toggle at every clock pulse, its J and K inputs are connected to Vcc or Vdd, where they will be “high” all the time.
The next flip-flop need only “recognize” that the first flip-flop’s Q output is high to be made ready to toggle, so no AND gate is needed.
However, the remaining flip-flops should be made ready to toggle only when all lower-order output bits are “high,” thus the need for AND gates.

**Procedure**

First, Quartus II software is opened and a new project is created using the New Project Wizard by giving a suitable project name. Then a Block Diagram/Schematic file is created. Required flip-flops (JK or T flip-flops) are selected from Primitives → Storage → Flip-Flop and placed on the schematic to form the counter. Input pins are added and named as CLK (clock) and RESET, and output pins are added for the counter outputs Q0, Q1, Q2, etc. All clock inputs of the flip-flops are connected to the common clock signal to ensure synchronous operation. The J and K inputs (or T inputs) are connected according to synchronous up-counter logic so that all flip-flops toggle simultaneously based on the clock. The reset input is connected to initialize the counter to zero. After completing the connections, the design is saved and compiled successfully. Then a University Program VWF file is created, clock and reset waveforms are applied, and functional simulation is run. The output waveforms are observed, and it is verified that the counter counts upward in binary sequence with each clock pulse, confirming the operation of the synchronous up counter
**PROGRAM**
```
module ex11(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out+1;
end
endmodule
module ex12(out,clk,rst);
input clk,rst;
output reg [3:0]out;
always @ (posedge clk)
begin
   if(rst)
     out<=0;
   else 
     out <= out-1;
end
endmodule
```
Developed by:Tejasvi S

RegisterNumber:25018480


**RTL LOGIC UP COUNTER**
up
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/8b3fe93c-b491-43ec-b788-44dae9a57470" />
down
<img width="1280" height="720" alt="image" src="https://github.com/user-attachments/assets/839f294e-957f-4097-9f2a-599ba9fbd4d8" />

**TIMING DIAGRAM FOR IP COUNTER**
<img width="1920" height="1080" alt="Screenshot (155)" src="https://github.com/user-attachments/assets/457e754a-7294-4829-b4b3-d058003a657c" />
<img width="1920" height="1080" alt="Screenshot (153)" src="https://github.com/user-attachments/assets/6b92332b-6abb-479d-88dc-0df7049a5590" />


**TRUTH TABLE**

<img width="673" height="719" alt="image" src="https://github.com/user-attachments/assets/0b99e556-7cb0-4aec-9600-72d25817a465" />

**RESULTS**
Thus, the Synchronous Up Counter was successfully designed and simulated using Quartus II, and the output waveforms were verified to count upward in correct binary sequence for each clock pulse.

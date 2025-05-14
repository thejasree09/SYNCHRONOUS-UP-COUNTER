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

Module sync_up_counter created with inputs clk, rst and output count [3:0].

4-bit register count declared to hold counter value.

On rising edge of clk, if rst==1, count resets to 0; else increments by 1.

Counter wraps around automatically after reaching 4'b1111 (15).



**PROGRAM**

![program](https://github.com/user-attachments/assets/d3a7b7bb-b6f4-41d8-bca8-24cb5eb7a8d2)


**RTL LOGIC UP COUNTER**

![simulation](https://github.com/user-attachments/assets/9ac7134b-4c1c-4ee8-aaa0-750475868ba8)



**TIMING DIAGRAM FOR IP COUNTER**

![waveform](https://github.com/user-attachments/assets/08df83b9-f03a-4678-8b93-dd0beabe9c5b)


**TRUTH TABLE**

![tt](https://github.com/user-attachments/assets/22fe97ea-2bb8-484b-8907-4374613893f8)


**RESULTS**

Simulation successful — Counter increments synchronously with clock and matches expected binary count sequence.

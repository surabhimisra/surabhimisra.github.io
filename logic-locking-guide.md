# A Technical Guide to Logic Locking for Chip Security
Strengthening integrated circuits against untrusted manufacturing and Trojan insertion.

## 1. Introduction
As semiconductor manufacturing becomes more global, securing the design and fabrication flow has become an important concern. Most design companies use the fabless model, which means fabrication happens in external foundries. This introduces two risks:
1. Unauthorized overproduction or IP theft  
2. Hardware Trojan insertion during mask preparation or ECO steps  

Logic locking introduces key-controlled gates into an ASIC so the chip works correctly only when the correct key is applied. It protects IP and increases the difficulty of malicious modification.

---

## 2. What is Logic Locking
Logic locking adds extra gates into a circuit that depend on a secret key. Without the key, the circuit produces incorrect outputs.

### Common key gate types
- XOR or XNOR gates  
- MUX-based key gates  
- Anti-SAT blocks  
- SFLL (Stripped Functionality Logic Locking)  

---

## 3. Simple XOR-Based Locking Example
Original RTL:
```verilog 
assign Y = A ^ B;
```
Locked Version:
```
assign Y_locked = (A ^ B) ^ Key[0];
```
If Key[0] is zero, the circuit behaves normally.
If it is one, the output is corrupted.

4. Structural Impact
When locking is added, it affects:
  -Fan-out
  -Logic depth
  -Switching activity
  -Combinational cones
  -Critical path behavior
These changes slow down reverse engineering and structural matching.

5. How Locking Helps Detect Trojans
Hardware Trojans often use rare triggers and quiet regions of logic. Locking disrupts this by:
  -Increasing switching entropy
  -Producing less predictable power signatures
  -Making Trojan payloads more detectable
  -Localizing suspicious activity
   
6. Power Analysis Overview
Power consumption can reveal Trojan activity.
P_total = P_static + P_dynamic
P_dynamic ∝ C_load * V^2 * f * switching_activity
Locked circuits modify switching activity, making Trojan-related anomalies easier to detect.

7. MUX-Based Lock Example
assign Y = Key[i] ? real_signal : dummy_signal;
Correct key selects the real signal.
Incorrect key selects the dummy path.

8. SAT Attack Notes
SAT attacks try to recover the key.
Ways to defend:
  -deeper locking
  -SFLL
  -Anti-SAT
  -re-synthesis
  -hiding XOR patterns

9. RTL Example
module locked_and4(
    input  wire [3:0] A,
    input  wire [3:0] Key,
    output wire Y
);
    wire temp0, temp1;
    
    assign temp0 = A[0] & A[1];
    assign temp1 = A[2] & A[3];

    assign Y = (temp0 ^ Key[0]) & (temp1 ^ Key[1]);
endmodule

10. Engineering Guidelines:
  1. Distribute key gates
  2. Combine locking with scan chain protection
  3. Test golden vs locked versions
  4. Measure switching profiles
  5. Evaluate SAT resistance
   
11. Tools
  1. Yosys
  2. Synopsys Design Compiler
  3. Cadence Genus
  4. TrustHub benchmarks
  5. SAT attack tools
  6. PrimeTime PX
  7. Python VCD processing scripts

12. Conclusion
Logic locking is a practical method for protecting integrated circuits against IP piracy and fabrication-time manipulation. It increases uncertainty for attackers and improves Trojan detectability.

This document is part of a larger set of hardware security and ASIC design notes.

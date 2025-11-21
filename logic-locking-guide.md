---
layout: default
title: "A Technical Guide to Logic Locking for Chip Security"
---

# A Technical Guide to Logic Locking for Chip Security

Strengthening integrated circuits against untrusted manufacturing and Trojan insertion.

## 1. Introduction

As semiconductor manufacturing becomes more global, securing the design and fabrication flow has become an important concern. Most design companies use the fabless model, which means fabrication happens in external foundries. This introduces two risks:

1. Unauthorized overproduction or IP theft  
2. Hardware Trojan insertion during mask preparation or ECO steps  

Logic locking introduces key controlled gates into an ASIC so the chip works correctly only when the correct key is applied. It protects IP and increases the difficulty of malicious modification.

---

## 2. What is Logic Locking

Logic locking adds extra gates into a circuit that depend on a secret key. Without the key, the circuit produces incorrect outputs.

### Common key gate types

- XOR or XNOR gates  
- MUX based key gates  
- Anti SAT blocks  
- SFLL (Stripped Functionality Logic Locking)  

---

## 3. Simple XOR Based Locking Example

Original RTL:

```verilog
assign Y = A ^ B;

---
layout: default
title: "Survey: A Survey on Hardware Trojans"
permalink: /paper-summaries/survey-hardware-trojans/
---


# Paper Summary: A Survey on Hardware Trojans  
**Authors:** Mohammad Tehranipoor and Farinaz Koushanfar  
**Published:** IEEE Design & Test of Computers, 2010

This is one of the earliest and clearest overview papers on hardware Trojans. It explains the basic terminology, Trojan structures, insertion points, and detection challenges. It is a great starting point before reading more advanced research.

---

## 1. Why I Chose This Paper
I wanted a simple, foundational understanding of hardware Trojans before diving into more advanced papers like TroLL or switching-activity-based detection. This survey paper covers the basics clearly and is very easy to summarize and relate to my own Trojan detection experiments.

---

## 2. What Problem the Paper Addresses
As the semiconductor supply chain became global, chip designers increasingly relied on external foundries. This introduces two major concerns:

1. Malicious insertion of extra circuitry  
2. Untrusted modifications during fabrication  

The paper explains the fundamental questions:
- What exactly is a hardware Trojan?  
- How can Trojans be inserted?  
- How do they hide?  
- Why are they so difficult to detect?

---

## 3. What Is a Hardware Trojan
The paper breaks down Trojans into two main components:

### **Trigger**
The part of the Trojan that activates under rare conditions.  
Examples:
- Rarely-toggling internal nets  
- Specific input patterns  
- Counters or timers  
- State machine sequences  

### **Payload**
The malicious behavior executed once the trigger activates.  
Examples:
- Leaking information  
- Modifying internal signals  
- Disabling functionality  
- Changing chip behavior temporarily or permanently

![HWT can be inserted anywhere](/images/HWT-trigger-payload.jpg)

This section forms the basis for many detection techniques we use today.

---

## 4. Types of Hardware Trojans

### **By Structure**
- **Combinational:** Trigger depends directly on input signals  
- **Sequential:** Trigger depends on sequences over time (harder to detect)  
- **Parametric:** Subtle changes to electrical characteristics (thresholds, delays)  

### **By Activation**
- Always-on  
- Triggered (rare events)  
- Time-based  
- Condition-based  

### **By Effect**
- Functional modification  
- Denial of service  
- Information leakage  
- Reliability degradation  

This classification helps in understanding how Trojans behave and why detecting them is challenging.

---

## 5. Where Trojans Are Inserted
The paper outlines insertion points across the chip design flow:

- RTL modification  
- Gate-level modification  
- During synthesis or optimization  
- At layout (GDSII)  
- During mask generation  
- At fabrication  
- Through untrusted third-party IP

![HWT can be inserted anywhere](/images/HWT-can-be-into-anywhere.jpg)

This is important because detection depends on where the Trojan was inserted.

---

## 6. Why Detecting Trojans Is Hard
The paper highlights several reasons:

- Trojans are intentionally small  
- Triggers are activated extremely rarely  
- Payloads can hide in unused logic  
- Attackers know the design well  
- Side-channel differences are tiny  
- Golden “reference” chips may be unavailable



This is exactly why switching activity, power traces, and rare nets become important.

---

## 7. Detection Techniques (High-Level)
The survey explains several detection categories:

### **1. Logic Testing**
Try to activate the Trojan by applying many input patterns.  
Challenge: triggers can be astronomically rare.

### **2. Side-Channel Analysis**
Measure:
- Power  
- Timing  
- EM emanations

![HWT can be inserted anywhere](/images/HWT-detection-power.jpg)

And compare against known-good chips.  
Challenge: process variation hides differences.

### **3. Functional Testing**
Observe if output deviates from expected behavior.  
Challenge: payload may only activate under narrow conditions.

### **4. Design-Time Analysis**
Static analysis, formal verification, netlist comparison.  
Challenge: Trojans can be inserted after synthesis.

### **5. Run-Time Monitoring**
On-chip sensors, parity checks, watchdogs.  

The paper gives a balanced overview, which is perfect for building intuition.

---

## 8. What I Found Interesting
The paper highlights a key insight:  
**The best Trojans target rare signals because they hide inside normal design noise.**

![HWT can be inserted anywhere](/images/HWT-trigger-payload.jpg)

This directly connects to my current work, where I compare switching activity across designs and observe how Trojans modify toggle patterns, especially on rare nets.

Another interesting point:  
**Detection is often easier when the design includes extra transformations like logic locking.**  
(This aligns with the papers I read on switching activity and TroLL.)

---

## 9. How This Connects to My Work
This survey paper sets the foundation for my ongoing project on hardware Trojan detection using:

- Rare-net analysis  
- Switching activity comparison (SAIF/VCD)  
- Logic-locking-induced switching changes  
- Power-based detectability  
- Structural visibility of Trojan inserts  

By understanding the basics from this survey, it becomes much easier to appreciate more advanced techniques like:

- TroLL  
- SFLL  
- Anti-SAT  
- Switching activity restriction  
- Structural similarity attacks  

---

## Final Takeaway
This survey is the perfect starting point for anyone entering hardware security. It explains Trojans in simple terms without heavy mathematics. Every more advanced paper builds on the concepts introduced here.

This summary will serve as the foundation for future deep dives into specific attack and detection techniques.

---
**Paper:** "A Survey on Hardware Trojans"  
**Authors:** Mohammad Tehranipoor and Farinaz Koushanfar  
**Source:** IEEE Design & Test of Computers, 2010  

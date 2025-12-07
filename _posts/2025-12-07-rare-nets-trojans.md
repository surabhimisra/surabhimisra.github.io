---
layout: post
title: "Understanding Rare Nets and Why Trojans Love Them"
permalink: /rare-nets-hardware-trojans/
date: 2025-12-07
---

# Understanding Rare Nets and Why Trojans Love Them

If you read any hardware Trojan research, you will keep seeing one phrase again and again: **rare nets**.  
They show up in Trust-Hub benchmarks, detection algorithms, research papers, and almost every Trojan insertion strategy.

This post explains:
- What rare nets actually are  
- Why attackers target them  
- How designers and researchers can detect Trojans using rare-net analysis  
- How this connects to my ongoing experiments with switching activity and power traces  

This is a beginner-friendly overview, and you can follow along even if you’re new to hardware security.

---

# 1. What Are Rare Nets?

A **rare net** is a signal in a digital circuit that toggles very infrequently during normal operation.

For example:
- A net that switches once every few thousand cycles  
- A deep internal signal far from primary inputs  
- Control logic that activates only in edge cases  
- Reset or debug-related signals  
- Rare combinations of internal states  

In many circuits, most signals toggle frequently.  
But a few remain **quiet** or **almost never active**.

These low-activity nets are the perfect hiding spots for Trojans.

---

# 2. Why Trojans Love Rare Nets

Attackers insert hardware Trojans in places where they will not be triggered accidentally during testing or normal operation.

Rare nets give them exactly what they want:

### • High Stealth  
Low toggle probability means test vectors rarely activate them.

### • Predictable Silence  
These nets almost never switch, so a Trojan tied to them is nearly invisible.

### • Stable Trigger Conditions  
Attackers can tie Trojan triggers to specific rare-net patterns (like `A & B & C = 1`), making accidental activation unlikely.

### • Minimal Power Footprint  
Since rare nets rarely toggle, the Trojan’s trigger circuitry also consumes very little dynamic power.

### • Hard to Reach Through Testing  
Functional testbenches and ATPG often fail to activate these nets because they require deep state exploration.

In summary:  
**Rare nets allow Trojans to hide quietly until a highly specific trigger activates them.**

---

# 3. How Rare Nets Help in Detecting Trojans

Interestingly, the same property that makes rare nets good hiding spots also helps in detection.

### **1. Low Baseline Activity = High Sensitivity**  
If a net rarely toggles, any unusual activity stands out immediately.

### **2. Power Deviations Become Noticeable**  
Even small Trojan-induced switching creates measurable transient spikes.

### **3. Useful for Switching Activity Comparison**  
Comparing toggle density before and after Trojan insertion highlights suspicious nets.

### **4. Enable Structural Analysis**  
Tools can mark nets with VS (Very Small) toggle probability and examine logic cones around them.

### **5. Combine Well with Logic Locking**  
Logic locking further reduces random switching, which amplifies anomalies in rare nets (based on the paper I summarized).

---

# 4. How to Identify Rare Nets

You can identify rare nets using:

### • Simulation-Based Analysis  
Generate VCD or SAIF files and compute toggle counts.

### • ATPG and Signal Probability Tools  
Use probabilistic models to detect rarely activated internal nodes.

### • Test Vector Analysis  
Compare switching activity under different workloads.

### • Structural Metrics  
Deep logic cones and unreachable states correlate with rare nets.
---

# 5. How Attackers Use Rare Nets

Attackers typically attach Trojan triggers to:

- Deep combinational nodes  
- Low-frequency control paths  
- Unused internal states  
- FSM states that never occur in normal operation  
- Signals tied to debug or test modes  

A simple Trojan example:

```verilog
if (rare_net1 & rare_net2) begin
    payload_reg <= payload_reg ^ 1'b1;
end
```
---
# 6. How Rare-Nets Factor Into My Research

### Rare-net analysis is central to the experiments I am running:

  - Inserting Trojans into rare nets
  - Comparing switching activity in locked vs unlocked designs
  - Analyzing toggle differences in clean vs Trojan versions
  - Measuring power trace deviations
  - Understanding how logic locking reshapes switching cones

### This aligns directly with research papers on:

  - Switching-activity-based detection
  - Transient power signatures
  - Structural Trojan detection
  - Logic locking + Trojan interactions

I will be publishing these experiments in my GitHub repository soon.

If you’re interested in hardware Trojans, switching activity, or logic locking, follow my Research Notes section here:
👉 [research notes](https://surabhimisra.github.io/research/)

Thanks for reading!
Feel free to reach out if you have questions or want a post on a specific topic.
---

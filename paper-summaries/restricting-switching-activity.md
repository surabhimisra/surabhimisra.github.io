---
layout: default
title: "Summary: Restricting Switching Activity Using Logic Locking to Improve Power Analysis-Based Trojan Detection"
permalink: /paper-summaries/restricting-switching-activity/
---

# Restricting Switching Activity Using Logic Locking to Improve Power Analysis-Based Trojan Detection  
**Paper Summary**

This paper investigates how logic locking can unintentionally improve the detectability of hardware Trojans by changing the switching activity inside a design. The authors show that when logic locking restricts internal switching, Trojan-triggered switching becomes easier to spot through power analysis.

---

## 1. Problem the Paper Addresses

Hardware Trojans are difficult to detect because:

- they are very small  
- they activate rarely  
- their switching activity blends into normal circuit noise  

Power analysis usually compares golden and suspect chips, but the Trojan’s power signature often gets buried inside baseline switching.

The question the paper explores is:  
**Can logic locking reduce switching noise so that Trojan-induced activity becomes more visible in power traces?**

---

## 2. Core Idea in Simple Terms

Logic locking inserts key-controlled gates such as XOR and XNOR into the circuit.  
This restructuring changes how internal nodes switch.

The authors observe:

**Locked circuits switch in a more controlled, less random manner.  
This reduction in switching noise amplifies the disturbances caused by Trojan activity.**

As a result, power differences between Trojan-free and Trojan-inserted designs become easier to detect.

---

## 3. What the Authors Did

The experiments use standard benchmark circuits.  
The authors:

1. Insert logic locking  
2. Insert different types of hardware Trojans (combinational and sequential)  
3. Run switching-activity simulations (VCD or SAIF)  
4. Map switching activity to estimated power  
5. Compare Trojan vs non-Trojan power traces for locked and unlocked circuits  
6. Evaluate how locking improves detection sensitivity  

The methodology tests diverse Trojan behaviors, sizes, and locations.

---

## 4. Key Findings

### **1. Logic locking reduces baseline switching activity**
Switching becomes less random, making deviations easier to see.

### **2. Trojan switching causes more visible disturbances in locked circuits**
The power difference is sharper and easier to isolate.

### **3. Rare nets become highly sensitive**
If a Trojan is placed in a low-activity region, even small switching becomes detectable after locking.

### **4. Power analysis becomes significantly stronger**
Locked designs amplify Trojan-related power deviations.

### **5. Full payload activation is not required**
Even partial trigger activation is enough to reveal the Trojan’s presence.

---

## 5. Why This Matters

This study shows that logic locking is not only useful for IP protection.  
It can also improve hardware Trojan detection by:

- lowering switching noise  
- increasing sensitivity to small disturbances  
- reshaping switching cones  
- making side-channel differences more pronounced  

This suggests a future direction where designers apply **security-aware locking strategies** to enhance detectability.

---

## 6. Weaknesses and Limitations

### **1. Assumes ideal key-gate distribution**
Real ASIC flows may not lock the most impactful regions.

### **2. Simplified power modeling**
Real silicon introduces PDN noise, parasitics, and variations that could blur switching differences.

### **3. Some Trojan placements remain hard to detect**
Not all regions benefit equally from switching restriction.

### **4. Requires accurate VCD or SAIF extraction**
Power estimation accuracy depends heavily on precise activity dumps.

### **5. Experiments are done on small benchmarks**
Scalability to large SoCs is unclear.

---

## 7. What I Found Most Interesting

The most interesting insight is the interaction between **logic locking** and **Trojan detectability**.

Logic locking was originally created for IP protection, but this paper shows it can also reshape switching behavior in ways that make malicious activity easier to spot.  

This connects directly to my research exploration on:

- switching-activity differences in locked vs unlocked circuits  
- rare-net Trojan insertion  
- VCD-based toggle analysis  
- side-channel signatures  

---

## 8. Suggested Diagrams to Add Later

- Locked vs unlocked switching pattern comparison  
- Power trace difference (Trojan vs clean) after locking  
- Rare-net Trojan placement example  
- Toggle heatmaps under locking  
- Key-gate insertion influence on switching cones  

---

## Citation

Nejat, A.; Kazemi, Z.; Beroulle, V.; Hely, D.; Fazeli, M.  
**"Restricting Switching Activity Using Logic Locking to Improve Power Analysis-Based Trojan Detection."**  
2019 IEEE 4th International Verification and Security Workshop (IVSW), 2019, pp. 49–54.  
**DOI:** 10.1109/IVSW.2019.8854402

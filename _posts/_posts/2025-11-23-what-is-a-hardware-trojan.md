---
layout: post
title: "What Is a Hardware Trojan?"
---

Most people are familiar with software malware and phishing, but there is a quieter kind of attack that hides in the chip itself. A hardware Trojan is a small malicious change to a circuit that is added somewhere in the design or manufacturing flow.

The key idea is simple. The original design is correct, but an extra piece of logic is inserted that only activates under rare conditions. Under normal tests, the chip seems fine. Under a special trigger, that extra logic can leak data, change outputs, or weaken security checks.

In practice, a hardware Trojan often has two parts:

1. A trigger that watches for a rare event, such as a specific input pattern or internal state.  
2. A payload that changes behavior, for example by flipping a bit, opening a backdoor, or bypassing a check.

Because the trigger is rarely activated, normal testing and functional verification may never see the Trojan fire. This is what makes these attacks interesting and hard to catch.

In my Hardware Trojan Lab series I work with very small RTL examples that show how this looks in code. A baseline module behaves as expected, and a Trojan version adds a few lines of Verilog that implement a rare trigger and a small payload. By running both through simulation and comparing waveforms, you can see exactly when the Trojan activates.

If you want a starting point to explore these ideas, you can:

- Look at the baseline and Trojan inserted designs in my lab repo.  
- Compare their simulation behavior and switching activity.  
- Read the companion logic locking guide to see how designers can try to protect against untrusted modifications.

Hardware Trojans are a deep research area, but even simple examples are enough to build intuition about how hardware can be attacked and how we might defend it.

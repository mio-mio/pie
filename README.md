# How Does PIE Change Memory Randomization?

## 1. Introduction
[Last time](https://github.com/mio-mio/aslr), I examined ASLR without PIE and observed how memory addresses behave.

In this experiment, I explore how enabling PIE changes the memory addresses' behavior.

Does PIE increase randomness of the executable itself, or does it only shift addresses together?

This experiment aims to observe how PIE affects address randomization, and to measure how much entropy is actually introduced.


## 2. What PIE Actually Does

PIE is typically used together with ASLR, as it allows the program itself to be loaded at different base addresses, enabling full randomization of the executable.

Without PIE, the executable is loaded at a fixed base address, even when ASLR is enabled as far as I tested in [last experiment](https://github.com/mio-mio/aslr).


## 3. Experiment Setup

To observe the effect of PIE, I compiled the vulnerable C program with and without PIE, and compared the results under ASLR.

I repeatedly executed the program and recorded the addresses to compare how it changes across runs.


## 4. Observations: What Changes

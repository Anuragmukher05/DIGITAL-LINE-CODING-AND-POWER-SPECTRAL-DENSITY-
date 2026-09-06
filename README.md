# DIGITAL-LINE-CODING-AND-POWER-SPECTRAL-DENSITY-

# Experiment 6 — Digital Line Coding and Power Spectral Density

## 📌 Aim

To generate and analyze common digital line-coding techniques using the same binary bit sequence and to compare their:

- Waveform characteristics
- DC content
- Bandwidth requirements
- Polarity
- Self-clocking capability
- Power Spectral Density (PSD)
- Running digital sum
- Behavior during long runs of identical bits

---

## 🎯 Objectives

1. Generate common digital line codes from a common bit sequence.
2. Compare the characteristics of different line-coding schemes.
3. Estimate and plot the normalized Power Spectral Density (PSD) using Welch's method.
4. Measure the average signal level and running digital sum.
5. Study the effect of long runs of identical bits.
6. Validate the generated waveforms through manual encoding of an 8-bit word.

---

## 🔢 Line Codes Implemented

The following six standard line codes are implemented:

1. **Unipolar NRZ**
2. **Polar NRZ**
3. **Polar RZ**
4. **Manchester**
5. **Differential Manchester**
6. **AMI (Alternate Mark Inversion)**

All line codes are generated from the **same binary bit sequence** so that a fair comparison can be made.

---

## 🧠 Theory

### 1. Unipolar NRZ

In Unipolar NRZ:

- Binary `1` → Positive voltage
- Binary `0` → Zero voltage
- The signal remains at the same level for the complete bit duration.

**Advantages**
- Simple implementation
- Low-frequency components are present

**Disadvantages**
- Significant DC component
- Poor synchronization for long runs of identical bits

---

### 2. Polar NRZ

In Polar NRZ:

- Binary `1` → `+A`
- Binary `0` → `-A`

The signal remains constant throughout the bit period.

**Advantages**
- Better use of signal power than unipolar NRZ
- Reduced DC component for balanced data

**Disadvantages**
- Synchronization becomes difficult during long runs of identical bits.

---

### 3. Polar RZ

In Polar RZ:

- Binary `1` → positive level followed by zero
- Binary `0` → negative level followed by zero

The signal returns to zero during every bit period.

**Advantages**
- Better synchronization
- More transitions than NRZ

**Disadvantages**
- Requires larger bandwidth than NRZ.

---

### 4. Manchester Coding

Manchester coding always contains a transition in the middle of every bit.

A common convention is:

- `1` → High-to-Low transition
- `0` → Low-to-High transition

> The exact polarity convention may be reversed as long as it is used consistently.

**Advantages**
- Self-clocking
- No DC component for balanced signaling
- Reliable synchronization

**Disadvantages**
- Requires approximately twice the transition rate of NRZ.

---

### 5. Differential Manchester

Differential Manchester always contains a transition in the middle of every bit.

The information is represented by the presence or absence of a transition at the **beginning of the bit period**.

For example, using one common convention:

- `0` → transition at beginning
- `1` → no transition at beginning

> The opposite convention is also valid if used consistently.

**Advantages**
- Self-clocking
- Less sensitive to signal polarity reversal
- Suitable for reliable data transmission

**Disadvantages**
- Requires relatively high bandwidth.

---

### 6. AMI — Alternate Mark Inversion

AMI uses three signal levels:

- Binary `0` → `0 V`
- Binary `1` → alternates between `+A` and `-A`

For example:

```text
Bits:       1   0   1   1   0   1
AMI:       +A   0  -A  +A   0  -A

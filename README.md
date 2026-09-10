# Multi-Stage Analog Signal Conditioner

This repository contains the IE2034 Analog Electronics assignment design for a **3-stage analog signal conditioner** that:

- passes signals in the **2 kHz to 12 kHz** band,
- attenuates out-of-band noise, and
- amplifies low-level inputs using **BJT common-emitter stages**.

---

## 1) Design objective

Create a compact analog front-end that accepts a low-amplitude AC input (sensor/microphone class), conditions it through filtering and gain stages, and provides a clean output primarily in the 2 kHz–12 kHz range.

---

## 2) Circuit overview (3 stages)

### Stage 1 — BJT pre-amplifier (common-emitter)
- Device: **BC547** (or equivalent small-signal NPN).
- Purpose: initial voltage gain and impedance conversion.
- Typical gain target: ~8 to 15 V/V.

### Stage 2 — RC high-pass section
- Purpose: reject low-frequency components below 2 kHz.
- Implemented as a first-order RC high-pass filter.

### Stage 3 — RC low-pass + BJT output amplifier
- RC low-pass portion limits content above 12 kHz.
- Final common-emitter BJT stage restores/sets required output amplitude.

---

## 3) Key specifications

- **Passband:** 2 kHz to 12 kHz  
- **Filter order:** first-order high-pass + first-order low-pass (band-limiting network)  
- **Active devices:** BC547 BJT stages  
- **Power supply:** single DC supply (commonly 9 V to 12 V for lab implementation)

---

## 4) Design calculations

Use the RC cutoff relationship:

\[
f_c = \frac{1}{2\pi RC}
\]

### High-pass cutoff (target \(f_{L} \approx 2\,\text{kHz}\))

Choose \(C_{HP} = 10\,\text{nF}\):

\[
R_{HP} = \frac{1}{2\pi f_{L} C_{HP}}
= \frac{1}{2\pi (2000)(10\times10^{-9})}
\approx 7.96\,\text{k}\Omega
\]

Nearest standard value: **8.2 k\(\Omega\)** (or 7.5 k\(\Omega\) based on availability).

### Low-pass cutoff (target \(f_{H} \approx 12\,\text{kHz}\))

Choose \(C_{LP} = 1\,\text{nF}\):

\[
R_{LP} = \frac{1}{2\pi f_{H} C_{LP}}
= \frac{1}{2\pi (12000)(1\times10^{-9})}
\approx 13.26\,\text{k}\Omega
\]

Nearest standard value: **13 k\(\Omega\)** or **12 k\(\Omega\)**.

### BJT stage gain (approximate)

For each common-emitter stage (emitter bypassed for AC gain):

\[
A_v \approx -\frac{R_C}{r_e}, \quad r_e \approx \frac{26\,\text{mV}}{I_E}
\]

Practical laboratory gain is typically reduced by loading and bias network effects; design and tune experimentally around the passband.

---

## 5) Suggested component set

- 2 × BC547 (or equivalent NPN BJTs)  
- Resistors for biasing networks (base divider, collector/emitter resistors)  
- \(R_{HP}\), \(C_{HP}\) for high-pass stage  
- \(R_{LP}\), \(C_{LP}\) for low-pass stage  
- Input/output coupling capacitors  
- Breadboard, DC source, oscilloscope/function generator

---

## 6) Setup and verification

1. Build bias networks for both CE amplifier stages and confirm DC operating points (transistor in active region).
2. Insert input coupling capacitor and Stage 2 high-pass RC section.
3. Insert Stage 3 low-pass RC section ahead of or around the output amplifier path as per your schematic.
4. Inject a sine wave (start with 100 mV\(_{pp}\)).
5. Sweep frequency from 100 Hz to 30 kHz and record output amplitude.
6. Verify:
   - attenuation below ~2 kHz,
   - strongest response in 2–12 kHz region,
   - attenuation above ~12 kHz.
7. Fine-tune resistor/capacitor values if cutoff frequencies shift due to tolerances/loading.

---

## 7) Notes for IE2034 submission

- Include final schematic (with actual values used), measured frequency response, and observed gain.
- Mention component tolerances and practical deviations from theoretical cutoff frequencies.
- If simulation was used (LTspice/Multisim), attach both simulated and measured plots.

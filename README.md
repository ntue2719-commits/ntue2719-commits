# Hi there! 👋 I'm Nguyen Tri Tue

🎓 **Undergraduate Student in Integrated Circuit Design**

I am interested in **RTL Design, FPGA Design, Digital IC Design, Computer Architecture, SoC Design, and Design Verification**.

I enjoy turning digital-system specifications into synthesizable RTL, building reference models and self-checking verification environments, and taking designs through synthesis, implementation, timing analysis, and FPGA validation.

---

## About Me

- 🎯 Focused on **RTL, FPGA, SoC, and Digital IC Design**
- 💻 Working with **Verilog, SystemVerilog, Python, and C**
- 🔬 Interested in **golden-model verification, deterministic regression, and hardware/software co-verification**
- ⚙️ Building FPGA accelerators with **AXI-based SoC integration**
- 🧠 Learning **UVM, FPGA timing closure, ASIC design flow, and computer architecture**
- 🚀 Working toward a career in **RTL / FPGA / ASIC / SoC / Design Verification**

---

## Technical Skills

**RTL & Verification**  
`Verilog` · `SystemVerilog` · `Self-checking Testbenches` · `Python Golden Models` · `Regression Testing`

**Programming**  
`Python` · `C`

**FPGA & EDA**  
`AMD/Xilinx Vivado` · `XSim` · `ModelSim` · `Synthesis` · `Implementation` · `Static Timing Analysis`

**SoC & Workflow**  
`AXI4-Lite` · `Linux MMIO` · `Git` · `GitHub` · `Technical Documentation`

---

# Featured Projects

## Median-Sobel Image Processing Accelerator on AMD Kria KR260

An FPGA SoC accelerator for **salt-and-pepper noise removal and Sobel edge detection**, implemented in Verilog-2001 and integrated with the ARM Processing System of the AMD Kria KR260.

```text
Noisy Image
    ↓
Median 3x3
    ↓
Sobel 3x3
    ↓
|Gx| + |Gy|
    ↓
Threshold
    ↓
Binary Edge Image
```

### Key Architecture

- Streaming 3×3 line-buffer architecture
- Median filter + Sobel Gx/Gy
- L1 gradient magnitude
- AXI4-Lite memory-mapped accelerator
- Input / Output frame memories
- FSM + Arbiter + Datapath
- Linux `/dev/mem` + `mmap()` control
- Python / ARM C / FPGA benchmark

### Verification Highlights

| Test | Result |
|---|---:|
| 64×64 | PASS |
| 512×512 | PASS |
| 640×480 | PASS |
| Datapath 512×512 | 516,133 checks, 0 errors |
| AXI two-frame regression | 24,041 checks, 0 errors |

Additional verification includes:

- Median: **618 checks, 0 errors**
- Threshold: **8,204 checks, 0 errors**
- Input Memory: **12,434 checks, 0 errors**
- Output Memory: **7,408 checks, 0 errors**

### FPGA Implementation

| Metric | Result |
|---|---:|
| Target | AMD Kria K26 |
| Clock | 100 MHz |
| LUTs | 3,560 |
| Registers | 3,406 |
| BRAM | 2 |
| DSP | 0 |
| WNS | +0.322 ns |
| WHS | +0.013 ns |
| Timing | **MET** |

### Physical KR260 Bring-Up

Verified on hardware:

- FPGA Manager and bitstream loading
- AXI register access
- Input MMIO
- START / DONE control
- Output MMIO
- Black-frame execution: **3600 / 3600 correct**

Native ARM C baseline:

```text
20 / 20 runs bit-exact
Mean kernel time = 4.817457 ms
```

### Current Hardware Status

Physical KR260 integration is operational.

For the controlled noisy-frame test:

```text
5 / 20 runs bit-exact
15 / 20 runs contain one repeated mismatch
```

The remaining mismatch is under physical FPGA investigation using timing analysis and planned ILA-based observation.

A validated CPU-to-FPGA speedup is intentionally **not reported** until FPGA kernel latency is measured using cycle-accurate hardware instrumentation.

🔗 [View Repository](https://github.com/ntue2719-commits/image-dsp-benchmark)

---

## FPGA SECDED + BPSK Communication Pipeline

A deterministic FPGA communication system combining **error correction, BPSK modulation, controlled channel errors, deterministic noise injection, UART communication, and end-to-end verification**.

```text
UART RX
   ↓
SECDED Encoder
   ↓
Bit-Flip Channel
   ↓
BPSK Modulator
   ↓
Noise Injector
   ↓
BPSK Demodulator
   ↓
SECDED Decoder
   ↓
UART TX
```

### Key Features

- Extended Hamming **SECDED (8,4)**
- BPSK modulation / demodulation
- LFSR-based error injection
- Signed deterministic noise injection
- UART RX/TX and protocol controller
- Python golden-model verification

### Verification Highlights

- **384 DSP transactions**
- **24,576 signal samples**
- **154,373 self-checking comparisons**
- **0 detected errors**
- **96 UART end-to-end requests**
- **577 system-level checks**

### FPGA Implementation

| Metric | Result |
|---|---:|
| Clock | 50 MHz |
| LUTs | 165 |
| Flip-flops | 213 |
| BRAM | 0 |
| DSP | 0 |
| WNS | +17.949 ns |
| Estimated power | 0.289 W |

🔗 [View Repository](https://github.com/ntue2719-commits/secDED-bpsk-fpga)

---

# Areas of Interest

- RTL Design
- FPGA Design
- Digital IC Design
- ASIC Design
- SoC Design
- Computer Architecture
- Design Verification
- FPGA Accelerators
- Hardware/Software Co-Verification

---

# Currently Learning

- Advanced SystemVerilog
- UVM Fundamentals
- FPGA Timing Closure
- ASIC Design Flow
- Computer Architecture
- AXI-Based SoC Design

---

# Engineering Workflow

```text
Specification
    ↓
Reference Model
    ↓
RTL Design
    ↓
Verification
    ↓
Synthesis
    ↓
Implementation
    ↓
Timing / Area / Power
    ↓
Hardware Bring-Up
```

My goal is to build reliable digital systems and contribute to **RTL, FPGA, ASIC, SoC, or Design Verification development**.

---

## Contact

- GitHub: [ntue2719-commits](https://github.com/ntue2719-commits)
- Email: [ntue2719@gmail.com](mailto:ntue2719@gmail.com)
- LinkedIn: **Coming Soon**

---

Thanks for visiting my GitHub profile!
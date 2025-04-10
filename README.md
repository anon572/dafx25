# **README.md**  

This repository contains multiple folders with processing scripts and an experimental dataset for analyzing real and synthetic diodes under various test conditions.  

## **Repository Structure**  

```
├── AD3-workspaces                          # Analog Discovery 3 workspace files (.dwf3work, .dwf3scope)
├── data-processing-py                      # Python scripts for processing and visualizing waveform/spectral data
│   └── img                                 # Images of waveforms and spectra
├── MATLAB                                  # MATLAB scripts for Total Harmonic Distortion, Signal-to-Noise-Ratio, and harmonic levels
├── ramp-offset                             # Ramp offset data
├── real-diodes-in-T00-L10-D00              # Real diode pair measurements in-circuit (various conditions)
│   ├── 100Hz-1V                            # Measurement at 100Hz, ±1V input
│   ├── 100Hz-2V
│   ├── 1kHz-1V
│   ├── 1kHz-2V
├── real-diodes-in-T00-L10-D10              # Similar structure for different test configurations
├── real-diodes-in-T10-L10-D00   
├── real-diodes-in-T10-L10-D10   
├── real-diodes-out                         # Real diode measurements outside of the circuit
├── synth-diodes-1f-1r-in-T00-L10-D00       # Synthetic diode measurements in-circuit
├── synth-diodes-1f-1r-in-T00-L10-D10
├── synth-diodes-1f-1r-in-T10-L10-D00
├── synth-diodes-1f-1r-in-T10-L10-D10
└── synth-diodes-1f-1r-out                  # Synthetic diode measurements outside the circuit
├── synth-diodes-2f-1r-in-2-1-T10-L10-D10   # Synthetic diode mod — 1 pair of diodes in series replacing diode D5 — measurements in-circuit
├── synth-diodes-2f-1r-in-4-1-T10-L10-D10   # Synthetic diode mod — Brett Miller's “HUEVOS GRANDES” — measurements in-circuit

```

---

## **Data Processing Scripts (`data-processing-py/` and `MATLAB/`)**  

The `data-processing-py/` folder contains Jupyter notebooks with Python scripts for:  

- Aggregating and conditioning waveform/spectral data  
- Plotting time-domain waveforms and frequency-domain spectra  
- Performing signal analysis on diode measurements  

The `img/` subfolder includes waveform and spectral images captured at various frequencies and voltages.  

The `MATLAB/` folder contains MATLAB scripts for Total Harmonic Distortion, Signal-to-Noise-Ratio, and harmonic levels, and processed data.  


---

## **Experimental Dataset Overview**  

Each dataset folder corresponds to a unique experimental setup, measuring either:  

- **real diodes** (e.g., `real-diodes-in-T00-L10-D10/`, `real-diodes-out/`),   
- **synthetic diodes** (e.g., `synth-diodes-in-T00-L10-D10/`),

in or out of the Boss DS1 circuit.  

### **Test Conditions**  

Each subfolder (`100Hz1V`, `1kHz2V`, etc.) represents a specific test condition, varying:  

- **Input Voltage:** 1V, 2V  
- **Input Frequency:** 100Hz, 1kHz  

Each test condition contains two key data files:  

- **`scope.csv`** – Time-domain waveform data from an oscilloscope  
- **`spectrum.csv`** – Frequency-domain data from a spectrum analyzer (amplitude in dBV, phase)  

---

## **Real Diode Pair Measurements**  

- **`real-diodes-out/`** – Measurements of real diode pairs in isolation (outside the DS1 circuit)  
- **`real-diodes-in-Txx-Lyy-Dzz/`** – Measurements of real diodes inside the DS1 circuit under different test configurations:  
  - **T (Tone):** `T00` (min) to `T10` (max)  
  - **D (Distortion):** `D00` (min) to `D10` (max)  
  - **L (Level):** Set to maximum (`L10`) in all cases  

---

## **Synthetic Diode Measurements**  

Synthetic diode measurements follow the same structure as real diode measurements but involve simulated or artificially created diodes rather than physical components. These experiments are useful for comparing synthetic and real diode behavior under controlled conditions, validating circuit simulations, or testing theoretical models. The dataset includes:

- **`synth-diodes-out/`** – Measurements of synthetic diodes outside the circuit, similar to the real diode out-of-circuit tests.
- **`synth-diodes-1f-1r-in-Txx-Lyy-Dzz/`** – Measurements of synthetic diodes inside the DS1 circuit under varying Tone (T), Level (L), and Distortion (D) configurations.
- **`synth-diodes-2f-1r-in-Txx-Lyy-Dzz/`** – Measurements of the synthetic diode configuration—1 pair of diodes in series replacing diode D5—inside the DS1 circuit under varying Tone (T), Level (L), and Distortion (D) configurations.
- **`synth-diodes-4f-1r-in-Txx-Lyy-Dzz/`** – Measurements of the synthetic diode configuration—2 parallel pairs of diodes in series replacing diode D5 (Brett Miller's “HUEVOS GRANDES” Mod)— inside the DS1 circuit under varying Tone (T), Level (L), and Distortion (D) configurations.

- **Subfolders (`100Hz1V`, `1kHz2V`, etc.)** – Contain synthetic diode response data under different voltage and frequency test conditions.



---

## **Analog Discovery 3 Workspaces (`AD3-workspaces/`)**  

This folder contains workspace files (`.dwf3work`, `.dwf3scope`) from the **Analog Discovery 3** tool, which were used for waveform generation and analysis and spectral analysis
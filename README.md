Guitar-Amp-Project
A fully custom solid-state guitar amplifier designed from the ground up in KiCad. The amp integrates a classic analog signal chain — preamp, tone stack, and power amp — with a microcontroller-driven effects engine covering everything from compression and EQ to chorus, delay, and reverb.
Contributors: Rohaan, Joey

Features
Amp Controls

Gain / Volume
3-band tone stack: Treble, Mid, Bass
Clean / Drive channel switching

Onboard Effects

Dynamics: Compression
Filter: EQ, Wah
Gain: Overdrive, Distortion, Fuzz
Modulation: Chorus
Time-based: Delay, Reverb
Utility: Chromatic Tuner


Architecture
The signal chain follows the industry-standard pedal ordering convention:
Guitar Input
    │
    ▼
Input Buffer
    │
    ▼
Tuner Tap ──────────────────────────────► Tuner Display
    │
    ▼
Preamp Stage (Clean / Drive)
    │
    ▼
Tone Stack (Treble / Mid / Bass)
    │
    ▼
Effects Block (MCU-driven)
  ├─ Compression
  ├─ EQ / Wah
  ├─ Fuzz / Overdrive / Distortion
  ├─ Chorus
  ├─ Delay
  └─ Reverb
    │
    ▼
Power Amp Stage
    │
    ▼
Speaker Output
The analog signal path handles the preamp character and tone shaping. The effects block routes audio through an ADC → MCU → DAC pipeline for modulation and time-based processing, keeping latency and noise minimal.

Hardware
BlockApproachPreampDiscrete op-amp stagesTone StackActive 3-band EQEffects EngineMicrocontroller (TBD) with I2S audio codecPower AmpClass AB solid-statePCB DesignKiCad

Repository Structure
Guitar-Amp-Project/
├── hardware/
│   ├── schematics/       # KiCad schematic files (.kicad_sch)
│   ├── pcb/              # KiCad PCB layout files (.kicad_pcb)
│   ├── bom/              # Bill of materials
│   └── datasheets/       # Component datasheets
├── firmware/
│   ├── src/              # MCU source code
│   └── include/          # Headers
├── docs/
│   ├── block-diagram.pdf
│   └── design-notes.md
└── README.md

Status

🔧 In active development — schematic and signal chain design in progress.


 Project scoped and architecture defined
 Schematic capture (KiCad)
 PCB layout
 Prototype build
 Firmware (effects engine)
 Testing & tuning


License
To be determined.
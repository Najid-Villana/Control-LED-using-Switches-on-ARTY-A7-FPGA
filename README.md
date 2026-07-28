# Arty A7-100T — Peripheral Playground

A hands-on learning project to get comfortable with the **Vivado design flow** (project creation → synthesis → implementation → bitstream → hardware programming) using the onboard peripherals of the [Digilent Arty A7-100T](https://digilent.com/reference/programmable-logic/arty-a7/start) FPGA board.

Each stage is a self-contained SystemVerilog design that introduces one new concept, building up in complexity from simple combinational logic to PWM and analog input handling.

## Board

- **Board:** Digilent Arty A7-100T
- **FPGA:** Xilinx Artix-7 (`xc7a100tcsg324-1`)
- **Tool:** Xilinx Vivado

## Roadmap / Stages

| Stage | Project | Concepts Introduced | Status |
|-------|---------|---------------------|--------|
| 1 | Switch → LED passthrough | Vivado project flow, XDC constraints, bitstream generation | ✅ Done |
| 2 | Debounced button counter | Clocked processes, sequential logic, debouncing | 🔲 Planned |
| 3 | PWM LED dimmer | PWM generation, timing counters | 🔲 Planned |
| 4 | RGB LED color mixer | Multi-channel PWM, resource sharing | 🔲 Planned |
| 5 | XADC analog input reader | IP integration, analog-to-digital pipeline | 🔲 Planned |
| 6 | Combined peripheral dashboard | Top-level integration, testbenches | 🔲 Planned |

## Repository Structure

```
arty-a7-peripherals/
├── stage1_switch_led/
│   ├── src/
│   │   └── top.sv
│   └── constraints/
│       └── arty_a7_100t.xdc
├── stage2_button_counter/      (coming soon)
├── stage3_pwm_dimmer/          (coming soon)
├── stage4_rgb_mixer/           (coming soon)
├── stage5_xadc_reader/         (coming soon)
└── README.md
```

## Getting Started

1. Open Vivado and create a new **RTL Project**.
2. Add the `src/*.sv` file(s) from the relevant stage folder as Design Sources.
3. Add the `constraints/*.xdc` file as a Constraints file.
4. Set the part to **`xc7a100tcsg324-1`**.
5. Run Synthesis → Run Implementation → Generate Bitstream.
6. Connect the Arty A7 via USB, open the Hardware Manager, auto-connect, and program the device.

## Stage 1: Switch → LED Passthrough

The simplest possible design — each of the 4 slide switches directly drives the corresponding onboard LED, with no clock involved. This stage exists purely to verify the full toolchain works end-to-end: Vivado project setup, pin constraints, synthesis, implementation, bitstream generation, and successfully programming the physical board.

## Demo

<!--
Add your demo video here. A few options:
1. Upload the video file directly to the repo (GitHub supports video preview for files under 10 MB,
   or up to 100 MB via git if you don't mind repo size).
2. Host on YouTube and embed a thumbnail link, e.g.:

   [![Watch the demo](https://img.youtube.com/vi/YOUR_VIDEO_ID/0.jpg)](https://www.youtube.com/watch?v=YOUR_VIDEO_ID)

3. Convert to a GIF (e.g. using ffmpeg) and embed directly - GIFs autoplay in the README, which
   looks best for short demos:

   ![Demo](docs/demo.gif)
-->

*(Video/GIF of the FPGA running will go here.)*

## Notes

Built as part of a self-directed learning track on FPGA design, alongside coursework in the INSPIRE IC Design Training program.

# H3-DAQ

Sensing / data acquisition board for an HV-H3TRB reliability tester (high voltage, high temperature, high humidity, reverse bias) for SiC and other wide-bandgap devices. CpE 190 / EEE 193A senior design, sponsored by DMEA.

## Layout

```
firmware/   STM32CubeIDE project (NUCLEO-G431RB)
host/       Python logger / plotter
docs/       Specs, schematics, test results
```

Interface spec (channels, pin map, packet format): see the H3-DAQ Firmware Interface Spec doc.

## Setup

1. Install **STM32CubeIDE 1.18.1** — everyone must use the same version.
2. Install Git (or GitHub Desktop) and clone this repo.
3. In STM32CubeIDE: **File → Import → General → Existing Projects into Workspace**, browse to `firmware/`, click Finish.
   - Do **not** check "Copy projects into workspace".
4. Build: **Project → Build All** (hammer icon). Flash: **Run → Debug** with the Nucleo plugged in.

## Rules

- Only the firmware lead edits `firmware/*.ioc` and regenerates code.
- Put your own code in `firmware/Core/Src/app/` and `firmware/Core/Inc/app/`, not in generated files. In generated files, write only between `/* USER CODE BEGIN */` and `/* USER CODE END */`.
- Work on a branch (`git checkout -b feature/<name>`), push it, and open a pull request into `main`.
- Never commit `Debug/`, `Release/` or `.settings/` (already in `.gitignore`).
- Open questions and tasks live in GitHub Issues.

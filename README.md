I originnally created this project for me but felt that as companies become gready
more people will try to perserve the oldies

# 🎮 EmulationStation Config Editor

A lightweight tool to simplify the creation and management of EmulationStation system configuration files.

This project focuses on improving the workflow of configuring emulators, cores, and launch commands by providing a structured and error-resistant approach instead of manually editing XML files.

---

## 🚀 Features

- 📂 Load and parse EmulationStation `es_systems.cfg`
- 🧠 Add emulator type for launch commands (RetroArch, Dolphin, etc.)
- 🎯 Automatic command generation (no manual command editing)
- 🔍 Validation of paths, cores, and executables
- 🧩 Modular emulator handling (per-emulator logic)
- 🔄 Safe export back to XML format

---

## 🧠 Core Idea

EmulationStation uses a simple XML structure, but configuring it manually becomes complex when dealing with:

- multiple emulators
- libretro cores
- command-line arguments
- fullscreen / batch modes

This tool separates concerns into:

### 1. Emulator Definitions
Internal logic for each emulator (e.g. RetroArch, Dolphin)

### 2. System Configuration
Per-platform setup (ROM paths, extensions, selected emulator)

### 3. Command Builder
Automatically generates correct launch commands based on emulator type

---

## 🧩 Example

Instead of writing this manually:

```xml
<system>
    <name>genesis</name>
    <fullname>Sega Genesis</fullname>
    <path>G:\.emulationstation\roms\sega32x</path>
    <extension>.bin</extension>
    <command>G:\.emulationstation\systems\RetroArch-Win64\retroarch.exe -L "G:\.emulationstation\systems\RetroArch-Win64\cores\genesis_plus_gx_libretro.dll" "%ROM_RAW%"</command>
    <platform>genesis</platform>
    <theme>genesis</theme>
  </system>

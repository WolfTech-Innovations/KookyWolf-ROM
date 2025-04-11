[![Build KookyWolf OS](https://github.com/WolfTech-Innovations/KookyWolf-ROM/actions/workflows/Build-KW.yml/badge.svg)](https://github.com/WolfTech-Innovations/KookyWolf-ROM/actions/workflows/Build-KW.yml)
# KookyWolf OS Build

This repository provides the build process for **KookyWolf OS**, a customized Android-x86-based operating system with ChromeOS/FydeOS-like features, branding, and a custom boot animation.

## Workflow

This repository is set up to automatically build **KookyWolf OS** through GitHub Actions using a self-hosted runner.

### Features:
- Android-x86 with KookyWolf OS branding.
- ChromeOS/FydeOS-style UI overlays.
- Custom boot animation.
- Linux apps support (Crostini-like functionality).
- Multi-window and multitasking features enabled.
- OTA updates with KookyWolf OS-specific updater.

---

## Workflow Overview

### Trigger:
This build is triggered manually via GitHub Actions `workflow_dispatch`.

### Jobs:

#### `build` job:
Runs on a **self-hosted runner** and executes the following steps:

1. **Checkout Source Code**
   - Pulls the latest source code from the repository.

2. **Install WSL and Ubuntu**
   - Installs the necessary dependencies and tools on the Windows Subsystem for Linux (WSL).

3. **Install Repo Tool**
   - Downloads and installs the `repo` tool for syncing Android source.

4. **Sync Android-x86 Source**
   - Initializes and syncs the Android-x86 repository for the build.

5. **Apply KookyWolf OS Branding and Tweaks**
   - Updates the Android build system with KookyWolf OS branding and makes ChromeOS/FydeOS tweaks.

6. **Apply ChromeOS/FydeOS Style UI Overlays**
   - Copies icons and themes from FydeOS to match the desired user interface.

7. **Download Custom Boot Animation**
   - Downloads a custom boot animation for the KookyWolf OS boot process.

8. **Add Boot Animation to ROM**
   - Integrates the downloaded boot animation into the ROM.

9. **Add Linux Apps Support (Crostini-like)**
   - Adds support for running Linux apps similar to the Crostini environment.

10. **Enable Windowed Mode and Multitasking Features**
    - Enables windowed mode and multitasking features for a more desktop-like experience.

11. **Enable OTA Updates and Customize Updater**
    - Integrates OTA update functionality and customizes the update interface with KookyWolf OS branding.

12. **Lunch and Build**
    - Prepares the environment and starts the build process for the KookyWolf OS image.

13. **Upload KookyWolf OS Build**
    - Uploads the generated ISO file for KookyWolf OS.

14. **Upload OTA Update ZIP**
    - Uploads the generated OTA update ZIP file.

---

## Usage

Once the workflow has completed, you will find the following artifacts:

- **KookyWolf OS ISO**: The final ISO image for KookyWolf OS, ready for installation.
- **KookyWolf OS OTA Update**: The OTA update ZIP file, which can be used for over-the-air updates.

These artifacts can be downloaded directly from the GitHub Actions artifacts section.

---

## Requirements

To build **KookyWolf OS**, you need:

- A self-hosted runner configured with WSL (Windows Subsystem for Linux).
- Ubuntu (or compatible Linux distribution) in WSL.
- Sufficient storage space to store the Android source code and build output.
  
Ensure that your runner meets these requirements to avoid build failures.

---

## Customization

You can modify the build steps to change the branding, boot animation, and other features by adjusting the respective scripts and resources in the repository.

---

## License

This project is open-source and released under the [MIT License](LICENSE). Feel free to contribute and make KookyWolf OS your own!

---

For more information or issues, feel free to open an issue or PR!

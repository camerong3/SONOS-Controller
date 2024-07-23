# Firmware Auto-Update Feature

The SONOS Controller firmware includes an automatic update feature that ensures your device always runs the latest version of the software. This document outlines how the auto-update process works and how you can configure it.

## How It Works

1. **Initialization:**
    - Upon startup, the ESP32 checks for updates by connecting to the GitHub API.
    - It compares the current firmware version with the latest version available in the repository.

2. **Version Check:**
    - The ESP32 sends a request to the GitHub repository to fetch the list of available firmware versions.
    - It parses the JSON response to identify the latest firmware version.

3. **Download Firmware:**
    - If a newer version is found, the ESP32 establishes a secure connection to download the new firmware file (`firmware.bin`) from the GitHub repository.
    - The firmware file is saved to the SPIFFS filesystem on the ESP32.

4. **OTA Update:**
    - The ESP32 initiates the OTA (Over-The-Air) update process using the downloaded firmware file.
    - The new firmware is flashed to the device, and the ESP32 restarts to apply the update.

## Configuration

### GitHub Repository Setup

Ensure your firmware files are correctly organized in the GitHub repository:
- Firmware files should follow the naming convention `firmware_vX.X.X.ino.bin`.
- Place the firmware files in the `firmware` directory of your repository.

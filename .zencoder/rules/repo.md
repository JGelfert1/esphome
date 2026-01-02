---
description: Repository Information Overview
alwaysApply: true
---

# ESPHome Experimente Information

## Repository Summary
This repository is a collection of **ESPHome** configuration files for various ESP32-based hardware, primarily focusing on the **ESP32-S3** with high-resolution displays (e.g., 480x480). It includes experiments with **LVGL** (Light and Versatile Graphics Library) for creating user interfaces on these displays.

## Repository Structure
The project is organized by hardware platforms or experimental setups.

- **`ESP32-S3 4848S040C/`**: Configurations for the Guition ESP32-S3-4848S040 display board.
- **`CYD/`**: (Empty) Likely intended for "Cheap Yellow Display" (ESP32-2432S028R) experiments.

## Projects

### ESP32-S3 4848S040C
This subproject contains configurations for the 4.0-inch 480x480 pixel ESP32-S3 display board.

**Configuration Files**: 
- `ESP32-S3 4848S040C/esp32-4848s040.yaml` (Main config)
- `ESP32-S3 4848S040C/dev-sensecapindicator.yaml` (Advanced config for SenseCAP Indicator)
- `ESP32-S3 4848S040C/test1.yaml` (Hardware testing config)

#### Language & Runtime
**Language**: YAML (ESPHome Configuration)
**Framework**: ESPHome using **esp-idf**
**Board**: `esp32-s3-devkitc-1`
**Variant**: `esp32s3`

#### Dependencies
**Main Components**:
- **lvgl**: Used for the graphical user interface.
- **st7701s**: Display driver for the 480x480 LCD.
- **gt911** or **ft5x06**: Touchscreen drivers.
- **Home Assistant API**: Integrated for sensor data and control.
- **pca9554**: I/O expander (used in some configurations).

#### Build & Installation
To compile and upload the configurations, use the ESPHome CLI:

```bash
# Example for the main configuration
esphome run "ESP32-S3 4848S040C/esp32-4848s040.yaml"
```

#### Key Resources
- **Display**: ST7701S RGB interface (480x480).
- **Touch**: GT911 (I2C).
- **UI Framework**: LVGL pages and widgets defined directly in YAML.
- **Secrets**: Uses `!secret` tags, requiring a `secrets.yaml` file (not included in the repo) for WiFi and API credentials.

#### Usage & Operations
- **OTA Updates**: Enabled for all configurations.
- **Logging**: Set to `DEBUG` level for troubleshooting.
- **Home Assistant**: Seamless integration via the `api` component.

#### Validation
- **Linting**: ESPHome validates YAML structure during the build process.
- **Hardware Testing**: `test1.yaml` provides a baseline for verifying display and touch functionality.

🕒 ESPHome Ok-to-wake Matrix Clock (8x8)

A feature-rich, Wi-Fi-connected smart clock built with an ESP32-C3 and a WS2812B 8x8 LED Matrix. This project is designed not just to tell time, but to serve as a visual sleep trainer for children using an "Ok-to-Wake" light signaling system.
✨ Features

    12-Hour Digital Display: Clean, custom-drawn 5x7 pixels font for maximum readability on a small grid.

    "Ok-to-Wake" System:

        Green Background: It's okay to get out of bed!

        Red Background: It's bedtime / stay in bed.

    Web-Based Configuration:

        Adjust Wake-up and Bedtime hours directly from your browser.

        Real-time Timezone selection (GMT offsets) via a dropdown menu.

    Minutes Progress Bar: A sleek 8-pixel bar at the bottom representing the progression of the current hour.

    Smart Connectivity:

        Captive Portal: Easy Wi-Fi setup if the clock can't connect to your network.

        SNTP Sync: Automatically fetches precise time from the internet.

        Status Indicator: A blinking red dot signals when the clock is waiting for a Wi-Fi or Time sync.

🛠 Hardware Requirements

    Microcontroller: ESP32-C3 (e.g., ESP32-C3-DevKitM-1).

    Display: 8x8 WS2812B Addressable RGB LED Matrix.

    Power: 5V USB Power supply.

🚀 Quick Start

    Install ESPHome: Ensure you have ESPHome installed (pip install esphome).

    Clone the Repo:
    Bash

    git clone https://github.com/YOUR_USERNAME/esphome-matrix-clock.git
    cd esphome-matrix-clock

    Compile & Flash:
    Connect your ESP32-C3 via USB and run:
    Bash

    esphome run matrix-clock.yaml

    Initial Setup:

        If no Wi-Fi is configured, the clock will create a hotspot named Matrix-Clock-Setup.

        Connect to it, enter your Wi-Fi credentials, and the clock will reboot and sync.

⚙️ Configuration

The clock's behavior can be customized in the matrix-clock.yaml file or via the Web UI:
Setting	Description
Timezone	Select your city/offset from the dropdown in the web dashboard.
Wake Hour	The hour (0-23) when the background turns Green.
Bedtime Hour	The hour (0-23) when the background turns Red.
Brightness	Control the intensity of the LEDs via the "Matrix Display" light entity.
📐 Pixel Mapping

The project assumes a "Z-shape" (zigzag) or standard row-major pixel mapping. If your matrix displays characters mirrored or distorted, adjust the pixel_mapper section in the YAML:
YAML

pixel_mapper: |-
  return (y * 8) + x; // Standard row-major

📄 License

This project is open-source and available under the MIT License.

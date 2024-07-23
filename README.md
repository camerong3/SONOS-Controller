# SONOS Controller

This project allows you to control SONOS speakers using an ESP32 microcontroller. The controller includes features such as automatic firmware updates, speaker volume control, LED brightness adjustment, and grouping of speakers.

## Requirements

- ESP32 microcontroller
- SONOS speakers
- Raspberry Pi running [node-sonos-http-api](https://github.com/jishi/node-sonos-http-api)
- NeoPixel LED strip
- LiquidCrystal_I2C LCD display
- Potentiometers for volume control
- Push buttons for menu navigation and play/pause functionality

## Features

- **Automatic Firmware Updates:** The controller can automatically update its firmware from a GitHub repository.
- **Volume Control:** Use potentiometers to adjust the volume of assigned SONOS speakers.
- **LED Brightness Control:** Adjust the brightness of the NeoPixel LEDs.
- **Speaker Grouping:** Group speakers for synchronized playback.
- **Web Interface for Dial Assignment:** Assign SONOS speakers to potentiometers using a web interface.

## Hardware Setup

1. **Connections:**
    - Connect the NeoPixel LED strip to pin `4` of the ESP32.
    - Connect the LCD display to the I2C pins (`SDA` and `SCL`) of the ESP32.
    - Connect the potentiometers to pins `34`, `35`, and `36` of the ESP32.
    - Connect push buttons to pins `0`, `25`, and `26` of the ESP32.

2. **Libraries:**
    - [WiFiManager](https://github.com/tzapu/WiFiManager)
    - [ArduinoJson](https://arduinojson.org/)
    - [Adafruit NeoPixel](https://github.com/adafruit/Adafruit_NeoPixel)
    - [LiquidCrystal_I2C](https://github.com/johnrickman/LiquidCrystal_I2C)

## Software Setup

1. **Clone the Repository:**
    ```sh
    git clone https://github.com/camerong3/SONOS-Controller.git
    ```

2. **Upload the Code:**
    - Open the project in the Arduino IDE.
    - Select the correct board and port for your ESP32.
    - Upload the code to the ESP32.

3. **Run the Node-Sonos-HTTP-API:**
    - Follow the instructions on the [node-sonos-http-api GitHub page](https://github.com/jishi/node-sonos-http-api) to set up and run the API on a Raspberry Pi.

## Usage

1. **Initial Setup:**
    - When the ESP32 starts, it will create a Wi-Fi access point named "SONOS Controller" with the password "0123456789".
    - Connect to this access point and open a web browser.
    - Navigate to the IP address shown on the LCD display to access the dial assignment interface.
    - Assign SONOS speakers to the dials and click "Assign".

2. **Controlling Speakers:**
    - Use the potentiometers to adjust the volume of the assigned SONOS speakers.
    - Use the menu button to navigate the menu on the LCD display and adjust LED brightness or group speakers.
    - Use the play/pause button to play or pause the assigned speaker.

3. **Automatic Firmware Updates:**
    - The controller will automatically check for firmware updates hosted on GitHub and perform OTA updates if a new version is available.

## Contributing

1. Fork the repository.
2. Create a new branch for your feature or bugfix.
3. Commit your changes.
4. Push your changes to your branch.
5. Create a pull request.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more information.

## Acknowledgments

- [node-sonos-http-api](https://github.com/jishi/node-sonos-http-api)
- [WiFiManager](https://github.com/tzapu/WiFiManager)
- [ArduinoJson](https://arduinojson.org/)
- [Adafruit NeoPixel](https://github.com/adafruit/Adafruit_NeoPixel)
- [LiquidCrystal_I2C](https://github.com/johnrickman/LiquidCrystal_I2C)

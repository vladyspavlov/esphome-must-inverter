# Must Solar Hybrid Inverter ESPHome Monitor

This repository contains an **ESPHome YAML configuration** for monitoring and controlling the Must Solar Inverter. The configuration leverages ESP32 with Modbus communication to interact with the inverter, providing detailed insights into its operational parameters and status.

## Features

- **Real-time Monitoring**:
  - Battery voltage, current, and power.
  - PV charger states, voltage, current, and power.
  - Inverter operational states including grid, load, and bus metrics.
  - Temperature readings for various components (radiator, transformer, etc.).
  
- **Energy Metrics**:
  - Accumulated power for charging, discharging, buying, selling, and load consumption.
  - AC and DC operational power and energy states.

- **Customizable Controls**:
  - Energy use modes (e.g., Solar-first, Utility-only).
  - Charger source priorities and voltage configurations.

## Prerequisites

- **Hardware**:
  - ESP32 board recommended. It also works with ESP8266.  
    I used WT32-ETH, [AliExpress](https://www.aliexpress.com/item/1005006074972994.html)
  - RS485 to UART board.  
    I used this one: [AliExpress](https://www.aliexpress.com/item/1005001621746811.html)
  - Optionally: USB cable, if you want to connect using USB port.  
    **Caution:** It may not work with your specific inverter model.  
    I used this one: [AliExpress](https://www.aliexpress.com/item/1005002358382000.html). Tested with PH(PV)18-5248 Pro.
    
- **Software**:
  - [ESPHome](https://esphome.io/) installed.
  - Home Assistant (optional but recommended).
 
## Connection scheme

Thanks to [@Rogero-](https://github.com/Rogero-). Here you can find more details and photos: [Discussion #9](https://github.com/vladyspavlov/esphome-must-inverter/discussions/9#discussioncomment-11593361).

<img src="https://github.com/user-attachments/assets/f21a1027-218e-4f2c-9b26-354641475daa" alt="Connection scheme picture" width="500" />

## Tested models

This config is compatible with all PV/PH18 and PV19 series inverters. The following models have been specifically tested either by me or the community:

- PV18-5248 Pro
- PH18-5248 Pro
- PV18-3024 VHM (Thanks to [@gjury](https://github.com/gjury))
- PV18-3224 VPM
- PV18-1012 VPM (Thanks to [@sstepane](https://github.com/sstepane))
- PV19-6248 EXP (Thanks to [@sergeysaley](https://github.com/sergeysaley))

## Demo video
[YouTube](https://youtu.be/0Ef8nHztPZQ)

## Usage

1. Clone this repository.
2. Replace placeholders (`wifi_ssid`, `wifi_password`, `api_key`, `ota_password`) with your specific configurations in the `yaml` file.
3. Flash the ESP32 board with this YAML file using ESPHome.
4. Connect the ESP32 to the inverter's communication port.
5. Access real-time data through Home Assistant or ESPHome dashboard.

## Notes

- Adjust logging levels (`INFO`, `DEBUG`) based on performance needs.

## License

This project is licensed under the MIT License. Feel free to use and modify the code as needed.

## References

https://gist.github.com/vladyspavlov/5ac21cb58923482eff8e7bbb2d0854b3

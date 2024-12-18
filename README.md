# smart-doorbell-shelly
A smart home doorbell integration using Shelly UNI and a generic doorbell transformer, enabling notifications and automation via MQTT or Home Assistant.

## Features
- Smart doorbell notifications
- Integration with smart home platforms
- Real-time monitoring of doorbell status
- Low-voltage control using Shelly UNI relay outputs

## Components
- Shelly UNI (Smart Wi-Fi device)
- Heidemann GT 3173 HDM (Doorbell transformer with 4V/8V/12V AC output)
- Heidemann Door Chime
- Existing doorbell wiring
- Optional: Smart home automation tools like Home Assistant, MQTT Broker, or Node-RED

## Wiring diagram
Here is the wiring diagram for the Shelly Uni to be connected in parallel with the button to detect the button press, without controlling the gong directly:

### Wiring: Shelly Uni in Parallel with Button (Gong is Detected, Not Controlled)

| **Component**      | **Designation**  | **Wiring**                                         |
|--------------------|------------------|----------------------------------------------------|
| Shelly Uni         | IN               | Parallel to the button - Contact 1                 |
|                    | I1               | Parallel to the button - Contact 2                 |
|                    | O                | Not connected (unused)                             |
|                    | N                | Neutral (from power source)                        |
|                    | L                | Live (from power source)                           |
| Button             | Button (1)       | Connection to IN and I1 on Shelly Uni              |
|                    | Button (2)       | Connection to + of the gong                        |
| Gong               | Gong (A)         | Connection to + of the button                      |
|                    | Gong (B)         | Connection to Neutral (N)                          |

### Operation:
- The button has a + terminal (for the gong) and connections to the Shelly Uni.
- The Shelly Uni is wired in parallel with the button, so it detects the button press (via IN and I1).
- The gong is not controlled by the Shelly Uni but is triggered directly by the button (via the + terminal of the button).
- The Shelly Uni only detects the button press and can be used for automations or notifications, without controlling the gong.
  
## Resources
- **Heidemann GT 3173 Datasheet** - `resources/Heidemann_70044_Transformator.pdf`
- **Heidemann Doorbell** - `resources/Heidemann_70169_Doorbell.pdf`
- **Shelly UNI Datasheet** - `resources/Shelly-UNI-User-Guide.pdf`

## Contributing
Contributions are welcome! Feel free to submit a pull request or open an issue for any bugs or feature requests.

## License
fail2ban-ops and all individual scripts are under the BSD 3-Clause license unless explicitly noted otherwise. Please refer to the [LICENSE](LICENSE).
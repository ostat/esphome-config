# Devices Directory

This directory contains your actual device configurations. Each YAML file represents a specific ESP device in your setup.

## Creating a New Device

1. Copy an example from the `../examples/` directory
2. Rename it to match your device (e.g., `living-room-light.yaml`)
3. Update the substitutions section with your device details
4. Modify the components (sensors, switches, etc.) as needed
5. Compile and upload:
   ```bash
   esphome run devices/your-device.yaml
   ```

## Best Practices

- Use meaningful names for your devices
- Always include common configurations (wifi, logger, api, ota)
- Use substitutions for repeated values
- Document special configurations with comments
- Test on the device before committing

## Example Device Structure

```yaml
substitutions:
  device_name: my-device
  friendly_name: "My Device"

esphome:
  name: ${device_name}
  platform: ESP8266
  board: esp01_1m

# Import common configs
<<: !include ../common/wifi.yaml
<<: !include ../common/logger.yaml
<<: !include ../common/api.yaml
<<: !include ../common/ota.yaml

# Add your specific components here
```

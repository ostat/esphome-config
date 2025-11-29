# Examples Directory

This directory contains example ESPHome configurations demonstrating common use cases and best practices.

## Available Examples

### basic-switch.yaml
A simple ESP8266-based smart switch with:
- Physical button input
- Relay control
- Status LED
- Perfect starting point for smart plugs or light switches

### temp-sensor.yaml
An ESP32-based temperature/humidity monitor with:
- DHT22 sensor integration
- WiFi signal monitoring
- Uptime tracking
- Useful for environmental monitoring

## Using Examples

1. Copy an example that matches your use case:
   ```bash
   cp examples/basic-switch.yaml devices/my-switch.yaml
   ```

2. Customize the configuration:
   - Update substitutions (device name, friendly name)
   - Adjust GPIO pins to match your hardware
   - Add or remove components as needed

3. Test the configuration:
   ```bash
   esphome config devices/my-switch.yaml
   ```

4. Compile and upload:
   ```bash
   esphome run devices/my-switch.yaml
   ```

## Contributing Examples

When adding new examples:
- Focus on common use cases
- Include comments explaining the configuration
- Use standard common components
- Test thoroughly before committing
- Update this README with a description

## More Examples

For more device configurations, check:
- [ESPHome Devices Database](https://devices.esphome.io/)
- [ESPHome Cookbook](https://esphome.io/cookbook/)

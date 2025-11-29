# ESPHome Configuration Repository

This repository contains custom ESPHome configurations for managing ESP8266/ESP32 devices.

## About ESPHome

[ESPHome](https://esphome.io/) is a system to control your ESP8266/ESP32 devices by simple yet powerful configuration files and control them remotely through Home Automation systems.

## Repository Structure

```
esphome-config/
├── devices/          # Device-specific configurations
├── common/           # Shared/reusable configuration components
├── examples/         # Example configurations
├── secrets.yaml      # Sensitive data (not tracked in git)
└── README.md         # This file
```

## Getting Started

### Prerequisites

1. Install ESPHome:
   ```bash
   pip install esphome
   ```

2. Clone this repository:
   ```bash
   git clone https://github.com/ostat/esphome-config.git
   cd esphome-config
   ```

3. Create your secrets file:
   ```bash
   cp secrets.yaml.example secrets.yaml
   ```

4. Edit `secrets.yaml` with your specific values (WiFi credentials, API passwords, etc.)

### Creating a New Device Configuration

1. Create a new YAML file in the `devices/` directory
2. Use the example configurations as a template
3. Include common components from the `common/` directory using `<<: !include`
4. Compile and upload:
   ```bash
   esphome run devices/your-device.yaml
   ```

## Common Components

The `common/` directory contains reusable configuration snippets:

- `wifi.yaml` - WiFi configuration with fallback AP
- `logger.yaml` - Logging configuration
- `api.yaml` - Home Assistant API configuration
- `ota.yaml` - Over-The-Air update configuration

Include these in your device configs:
```yaml
<<: !include common/wifi.yaml
<<: !include common/logger.yaml
```

## Security

⚠️ **Important**: Never commit `secrets.yaml` to version control! This file contains sensitive information like WiFi passwords and API keys.

The `.gitignore` file is configured to exclude:
- `secrets.yaml` - Your secrets file
- `.esphome/` - Build artifacts
- `*.bin` - Compiled binaries

## Example Usage

Check the `examples/` directory for sample configurations demonstrating common use cases.

## Contributing

1. Create device configurations in the `devices/` directory
2. Share reusable components in the `common/` directory
3. Update this README if adding new patterns or structures

## Resources

- [ESPHome Documentation](https://esphome.io/)
- [ESPHome Devices Database](https://devices.esphome.io/)
- [Home Assistant](https://www.home-assistant.io/)

## License

This repository is for personal use. See individual device configurations for specific licensing information.
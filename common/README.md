# Common Directory

This directory contains reusable configuration components that can be shared across multiple devices.

## Available Components

### wifi.yaml
Standard WiFi configuration with fallback AP. Includes:
- WiFi credentials from secrets
- Fallback hotspot configuration
- Captive portal

### logger.yaml
Logging configuration with INFO level by default.

### api.yaml
Home Assistant API configuration with encryption.

### ota.yaml
Over-The-Air update configuration for easy firmware updates.

## Using Common Components

Include components in your device configuration:

```yaml
<<: !include ../common/wifi.yaml
<<: !include ../common/logger.yaml
<<: !include ../common/api.yaml
<<: !include ../common/ota.yaml
```

## Creating New Common Components

When creating reusable components:
1. Keep them generic and parameterizable
2. Use secrets for sensitive data
3. Use substitutions for customizable values
4. Document the component's purpose and usage
5. Test with multiple devices before committing

## Advanced Usage

You can override specific parts of common components in your device config by redefining them after the include statement.

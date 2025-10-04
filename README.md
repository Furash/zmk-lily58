# Lily58 with Dual Nice!View Displays

This repository contains a ready-to-flash ZMK configuration for the Lily58 split keyboard with dual Nice!View displays.

## Configuration Overview

### Left Half (Central)
- **Role**: Central (master)
- **USB Logging**: ✅ Enabled
- **Display**: Nice!View with full widgets
- **Power Management**: Optimized for USB connection
- **File**: `config/lily58_left.conf`

### Right Half (Peripheral)
- **Role**: Peripheral (slave)
- **USB Logging**: ❌ Disabled (battery optimization)
- **Display**: Nice!View with full widgets
- **Power Management**: Deep sleep enabled
- **File**: `config/lily58_right.conf`

## File Structure

```
zmk-lily58/
├── build.yaml                 # GitHub Actions build configuration
├── README.md                  # This file
└── config/
    ├── lily58.conf           # Base configuration (shared)
    ├── lily58_left.conf      # Left half specific config
    ├── lily58_right.conf     # Right half specific config
    ├── lily58.keymap         # Keymap definition
    └── west.yml              # Zephyr manifest
```

## Key Features

- ✅ Dual Nice!View displays on both halves
- ✅ Proper split keyboard configuration
- ✅ USB logging on left half only (for debugging)
- ✅ Battery optimization on right half
- ✅ ZMK Studio support for real-time keymap updates
- ✅ Display widgets: layer status, battery, output status
- ✅ Correct ZMK key names (LPAR, RPAR, LBRC, RBRC)

## Flashing Instructions

1. **Build the firmware** using GitHub Actions or ZMK build system
2. **Flash left half** with `lily58_left` firmware (central with USB logging)
3. **Flash right half** with `lily58_right` firmware (peripheral without USB logging)
4. **Pair the halves** - they should automatically connect via Bluetooth

## Display Widgets

Both halves show:
- Current layer status
- Battery percentage
- Output status (USB/BLE)
- Connection status

## Power Management

- **Left half**: USB logging enabled, no deep sleep (connected via USB)
- **Right half**: Deep sleep enabled, optimized for battery life

## Troubleshooting

- If halves don't pair, reset both and try again
- USB logging is only available on the left half
- Right half will sleep when idle to save battery
- Both displays should show the same information when connected

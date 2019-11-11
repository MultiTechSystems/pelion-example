# Pelion Client Mbed OS Example

This is a simplified example with the following features:
- Mbed OS 5.14.1 and Pelion Device Management Client 4.0.0
- Support for FW Update
- 200 lines of code + credential sources

# Developer guide

This section is intended for developers to get started, import the example application, compile and get it running on their device.

## Requirements

- Mbed CLI version >= 1.10.0

  For instructions on installing and using Mbed CLI, please see our [documentation](https://os.mbed.com/docs/mbed-os/latest/tools/developing-mbed-cli.html).

- Generate and install your API key `CLOUD_SDK_API_KEY`
   For instructions on how to generate your API key, please see the [documentation](https://cloud.mbed.com/docs/current/integrate-web-app/api-keys.html#generating-an-api-key).

   Next install your API key in mbed CLI
   `mbed config -G CLOUD_SDK_API_KEY ak_1MDE1...<snip>`

   You should generate your own API key. Pelion Device Management is available for any Mbed developer. Create a [free trial](https://os.mbed.com/pelion-free-tier).

## Deploying

    git clone https://github.com/felser/mbed-os-example-pelion
    cd mbed-os-example-pelion
    git checkout Dragonfly-F413RH
    mbed deploy

## Compiling

    mbed target MTS_DRAGONFLY_F413RH
    mbed toolchain GCC_ARM
    mbed device-management init -d arm.com --model-name example-app --force -q
    mbed compile

## Program Flow

1. Initialize, connect and register to Pelion DM
2. Interact with the user through the serial port (115200 bauds)
   - Press enter through putty/minicom to simulate button
   - Press 'i' to print endpoint name
   - Press Ctrl-C to to unregister
   - Press 'r' to reset storage and reboot (warning: it generates a new device ID!)

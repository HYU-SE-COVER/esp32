## Functions Description

1. **`blink_led(void)`**
    - **Purpose**: This function turns the LED on or off depending on the current state of the LED.
    - **For addressable LED strips**: It sets the color value of the LED or turns off all pixels.
    - **For GPIO**: It changes the GPIO level to turn the LED on or off.
    - **Note**: The LED in esp32s3 has RGB, hence it communicates via SPI. The `led_strip_set_pixel(led_strip, 0, 0, 0, 32);` function call indicates the setting of color values. It provides parameters like which LED in a chain of LEDs (index), and the r, g, b values.

2. **`configure_led(void)`**
    - **Purpose**: This function does the initial setup required to control the LED.
    - **For addressable LED strips**: It initializes the LED strip based on the given GPIO and number of pixels and turns off all LEDs. Additional setup is done based on the backend (RMT or SPI) of the LED strip.
    - **For GPIO**: It initializes the GPIO pin and sets it to output mode.

3. **`app_main(void)`**
    - **Purpose**: This is the main function that runs on the ESP32S3. It sets up the LED and then repeatedly toggles the LED state, resulting in the blinking behavior.

# 3.5inch RPi LCD (B)

### Description:

This is a 3.5inch TFT LCD with resistive touch panel, has 480x320 resolution. Can support any revision of Raspberry Pi. Driver is provided for Raspbian/Ubuntu Mate/kali. And this is an IPS screen which has wider viewing angle.

### Website:

CN:http://www.waveshare.net/shop/3.5inch-RPi-LCD-B.htm

EN:https://www.waveshare.com/3.5inch-RPi-LCD-B.htm

### WIKI:

CN:http://www.waveshare.net/wiki/3.5inch_RPi_LCD_(B)

EN:https://www.waveshare.com/wiki/3.2inch_RPi_LCD_(B)

### LCD35B Display Setup for Raspberry Pi
**Compatibility & Driver Information (Kali Linux 2025.2 ARM Images and Newer)**
This guide provides instructions for setting up the LCD35B display on your Raspberry Pi. While primarily tested on **Kali Linux for Raspberry Pi**, the steps should also be compatible with other Raspberry Pi OS versions. This specific solution addresses driver compatibility for **Kali Linux 2025.2 ARM images and newer**.

**Prerequisites:**
* A Raspberry Pi running Raspberry Pi OS or Kali Linux for Raspberry Pi.
* Git installed.
* Internet connection.

**Setup Steps:**

1.  **Clone the project to your home directory:**
    Open a terminal and execute the following commands to clone this project into your home directory (e.g., `/home/kali/` or `~/`):
    ```bash
    git clone https://github.com/afrankwudev/LCD35B-show-V2-Fix.git
    ```

2.  **Update your system and install necessary dependencies:**
    ```bash
    sudo apt update
    sudo apt install -y build-essential debianutils xserver-xorg-input-evdev cmake libraspberrypi-dev libraspberrypi0
    ```

3.  **Compile `rpi-fbcp`:**
    ```bash
    cd ./LCD35B-show-V2-Fix/rpi-fbcp/build
    sudo rm -rf CMakeCache.txt CMakeFiles/

    # Generate Makefile using CMake
    sudo cmake ..

    # Compile the program
    sudo make
    ```
    *   **Note:** If `make` fails, try removing `sudo` from `sudo make` and run `make` again. Sometimes, error messages are clearer without `sudo`.

4.  **Run the LCD35B display program:**
    After `rpi-fbcp` compilation is complete, navigate back to the main project directory and run your display program.
    ```bash
    cd ~/LCD35B-show-V2-Fix
    sudo ./LCD35B-show-V2
    ```
    *   **Note:** Running `./LCD35B-show-V2` requires `sudo` privileges because it needs to interact directly with the display hardware and system resources.

**Troubleshooting:**
*   If you encounter compilation errors, please check the error messages and ensure all dependencies are correctly installed.
*   If the display does not respond, verify your hardware connections and ensure that your Raspberry Pi has booted correctly into the graphical interface.

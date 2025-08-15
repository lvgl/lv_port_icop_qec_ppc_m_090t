**:rocket: This repository is available in the [LVGL Project Creator](https://lvgl.io/tools/project-creator), making it easy to create and customize a new project in just a few clicks.**

# LVGL ported to iCOP QEC-PPC-M-090T

## Overview

The iCOP QEC-PPC-M-090T is a capable, fully-featured industrial HMI.
It has a specialized 533 MHz 32-bit x86 CPU. The programming environment
is Arduino. The fusion of the mature x86 architecture with the Arduino
ecosystem opens up powerful application opportunities.
There is a separate dedicated core for EtherCAT.

## Buy

(Coming soon...)

## Benchmark

The benchmark is of `LVGL_Arduino` in this repo.

<a href="https://www.youtube.com/watch?v=0TSrAsCWQlw">
    <img src="https://github.com/user-attachments/assets/ad43cb34-e40d-4c93-b670-b6ecf11743c2" width="75%">
</a>

| Name                      | Avg. CPU | Avg. FPS | Avg. time | render time | flush time |
| :------------------------ | -------: | -------: | --------: | ----------: | ---------: |
| Empty screen              | 78%      | 21       | 30        | 2           | 28         |
| Moving wallpaper          | 88%      | 21       | 40        | 5           | 35         |
| Single rectangle          | 18%      | 57       | 2         | 0           | 2          |
| Multiple rectangles       | 75%      | 40       | 18        | 1           | 17         |
| Multiple RGB images       | 45%      | 57       | 6         | 1           | 5          |
| Multiple ARGB images      | 63%      | 55       | 9         | 5           | 4          |
| Rotated ARGB images       | 78%      | 42       | 17        | 15          | 2          |
| Multiple labels           | 80%      | 37       | 20        | 11          | 9          |
| Screen sized text         | 92%      | 10       | 88        | 55          | 33         |
| Multiple arcs             | 85%      | 29       | 27        | 11          | 16         |
| Containers                | 30%      | 52       | 4         | 2           | 2          |
| Containers with overlay   | 84%      | 16       | 52        | 25          | 27         |
| Containers with opa       | 39%      | 55       | 7         | 5           | 2          |
| Containers with opa_layer | 57%      | 43       | 14        | 12          | 2          |
| Containers with scrolling | 89%      | 15       | 56        | 24          | 32         |
| Widgets demo              | 92%      | 12       | 65        | 39          | 26         |
| All scenes avg.           | 68%      | 35       | 28        | 13          | 15         |

## Specification

### CPU and Memory
- **CPU:** 533 MHz Vortex86EX2 32-bit x86 CPU
- **RAM:** 512MB/1GB DDR3
- **Flash:** 2GB SLC eMMC, 32MB SPI Flash

### Display and Touch
- **Resolution:** 1024x600
- **Display Size:** 9"
- **Interface:** VGA
- **Color Depth:** 16-bit
- **Technology:** TFT
- **DPI:** 132 px/inch
- **Touch Pad:** Resistive

### Connectivity
- Ethernet
- USB x3
- Headphone

## Getting started

### Hardware setup
- Connect the four ferruled wires to the Vs and Vp power inputs.
  Match the two red wires with the two red receptacles and the
  two black wires with the two black receptacles. Connect the
  barrel-jack connector to the wire bundle. Plug the adapter in.
- Connect a USB C cable to your PC.

### Software setup
1.  Download [the 86Duino Coding IDE 501 from here](https://www.qec.tw/software/).
2.  Extract the zip file.
3.  Launch 86duino.exe. No installation required. The IDE will open.
4.  Download [this pre-configured LVGL Arduino library package](https://github.com/acen2009/lvgl/archive/refs/heads/master.zip).
5.  In the 86Duino IDE, go to **Sketch > Include Library > Add .ZIP Library**. Select the downloaded LVGL library ZIP file
    you downloaded. It will be extracted to **C:\\Users\\[YourName]\\Documents\\86Duino\\libraries**.
6.  Copy **Documents\\86Duino\\libraries\\lvgl-master\\lv_conf_template.h** to **Documents\\86Duino\\libraries\\lv_conf.h**.
7.  Edit the new file so that `#if 0` on line 15 is `#if 1`.
8.  Restart the 86Duino IDE.

### Run the project
1.  Go to **File > Examples > lvgl > arduino > LVGL_Arduino**. Wait for the new window to open. Note that **lvgl** will be at
    the very bottom of **File > Examples**.

    OR

    As an alternative to the previous step, you may open the LVGL_Arduino.ino file from this repo. Use **File > Open**.

2.  Select the board "QEC PPC 9" under **Tools > Boards**.
3.  Select the correct COM port under **Tools > Port**. Ensure the device is connected.
4.  Click the the Upload button to build and upload the project to the device.

### Debugging
- Open the Serial Monitor by clicking the Serial Monitor button in the top-right.
  Ensure the baud rate is set to 115200. Logged messages will appear here.

## Notes

## Contribution and Support

If you find any issues with the development board feel free to open an Issue in this repository. For LVGL related issues (features, bugs, etc) please use the main [lvgl repository](https://github.com/lvgl/lvgl).

If you found a bug and found a solution too please send a Pull request. If you are new to Pull requests refer to [Our Guide](https://docs.lvgl.io/master/CONTRIBUTING.html#pull-request) to learn the basics.


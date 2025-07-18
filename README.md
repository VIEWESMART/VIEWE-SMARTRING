<h1 align = "center">SmartRing</h1>

<p align="center" width="90%">
    <img src="image/smartring.png" alt="">
</p>

## **English | [中文](./README_CN.md)**

## Version iteration:
|   Development board Version   |  Screen size   |   Resolution  | Update date        |Update description|
| :-------------------------------: | :-------------------------------: | :-------------------------------: | :-------------------------------: |:-------------------------------: |
| SMARTRING | 1.75-inch |  466*466  |2024-07-23      | Original version   |

## PurchaseLink

| Product                     | SOC           |  FLASH  |  PSRAM   | Link                   |
| :------------------------: | :-----------: |:-------: | :---------: | :------------------: |
| SMARTRING   | ESP32S3R8 |   16M   | 8M (Octal SPI) |  |

## Directory
- [Describe](#describe)
- [Module](#module)
- [PinOverview](#pinoverview)
- [QuickStart](#quickstart)
- [FAQ](#faq)
- [Schematic](#Schematic)
- [Information](#information)
- [DependentLibraries](#dependentlibraries)

## Describe

SMARTRING is a development board with square 1.75-inch 466 * 466 resolution display, based on ESP32S3, suitable for the development of microcontroller projects with display.


## Module

### 1.MCU

* Chip: ESP32-S3-R8
* PSRAM: 8M (Octal SPI) 
* FLASH: 16M
* For more details, please visit[Espressif ESP32-S3 Datashee](https://www.espressif.com.cn/sites/default/files/documentation/esp32-s3_datasheet_en.pdf)

### 2. Screen

* Size: 1.75-inch AMOLED screen
* Resolution: 466x466px
* Screen type: IPS
* Driver chip: CO5300
* Compatibility library:  ESP32_Display_Panel
* Bus communication protocol: QSPI
* For more details, please visit [display datasheet](https://github.com/VIEWESMART/VIEWE-SMARTRING/blob/main/datasheet/ALL-UEOL018VG-RA31-A001A%20V1.0%20SPEC.pdf)

### 3. Touch

* Touch Chip: CST9217
* Bus communication protocol: IIC
* For more details, please visit [Touch datasheet](https://github.com/VIEWESMART/VIEWE-SMARTRING/blob/main/datasheet/CST9217.pdf)

## PinOverview

|ESP Pin NO.|	 FUNCTION|
| :------------------------: | :-----------: |
|GPIO0 | BOOT|
|GPIO1 | SDMMC_D1|
|GPIO2 | SDMMC_D0|
|GPIO3 | SDMMC_SCK|
|GPIO4 | SDMMC_CMD|
|GPIO5 | SDMMC_D3|
|GPIO6 | SDMMC_D2|
|GPIO7 | LCD_QSPI_CS|
|GPIO8 | LCD_QSPI_D1|
|GPIO9 | LCD_QSPI_D3|
|GPIO10 | LCD_TE|
|GPIO11 | LCD_RST|
|GPIO12	| LCD_QSPI_D0|
|GPIO13 | LCD_QSPI_SCL|
|GPIO14	| LCD_QSPI_D2|
|GPIO15 | XSMT|
|GPIO16	| I2S_DAC_LRCK/WS|
|GPIO17 | I2S_DAC_DIN|
|GPIO18 | I2S_DAC_BCK|
|GPIO19 | USB_N|
|GPIO20 | USB_P|
|GPIO21 | IMU_INT1|
|GPIO38 | IMU_INT2|
|GPIO39 | RGB_DIN|
|GPIO40 | LCD_VCIEN|
|GPIO41 | TP_SDA|
|GPIO42 | TP_INT|
|GPIO43 | UART0_RX|
|GPIO44	| UART0_TX|
|GPIO45 | TP_SCL|
|GPIO46	| TP_RST|

## QuickStart

### Examples Support

| Example | Support IDE And Version| Description | Picture |
| ------  | ------  | ------ | ------ | 
| [ESP-IDF](./examples/dep-idf) | `[ESP-IDF V5.1/5.2/5.3]` | idf driver example code |  |
| [SquareLinePorting](./examples/arduino) | `[Arduino IDE][esp32_v3.1.0]` | SquareLine porting example for Arduino |  |


| Firmware | Description | Picture |
| ------  | ------  | ------ |
| [ESP-IDF]() | Original |  |

### PlatformIO
1. Install[VisualStudioCode](https://code.visualstudio.com/Download),Choose installation based on your system type.

2. Open the "Extension" section of the Visual Studio Code software sidebar(Alternatively, use "<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>X</kbd>" to open the extension),Search for the "PlatformIO IDE" extension and download it.

3. During the installation of the extension, you can go to GitHub to download the program. You can download the main branch by clicking on the "<> Code" with green text.

4. After the installation of the extension is completed, open the Explorer in the sidebar(Alternatively, use "<kbd>Ctrl</kbd>+<kbd>Shift</kbd>+<kbd>E</kbd>" go open it),Click "Open Folder", find the project code you just downloaded (the entire folder), then find the PlatformIO folder and click "Add". At this point, the project file will be added to your workspace.

5. Open the "platformio.ini" file in the project folder (PlatformIO will automatically open the "platformio.ini" file corresponding to the added folder). Under the "[platformio]" section, uncomment and select the example program you want to burn (it should start with "default_envs = xxx") Then click "<kbd>[√](image/4.png)</kbd>" in the bottom left corner to compile,If the compilation is correct, connect the microcontroller to the computer and click "<kbd>[→](image/5.png)</kbd>" in the bottom left corner to download the program.

### Arduino
### Arduino Framework ([Novice tutorial](https://github.com/VIEWESMART/VIEWE-Tutorial/blob/main/Arduino%20Tutorial/Arduino%20Getting%20Started%20Tutorial.md))
1. **Install[Arduino](https://www.arduino.cc/en/software)**
- Choose installation based on your system type.
- Newcomers please refer to the [beginner's tutorial]().

2. **Install ESP32 SDK**

- Open Arduino IDE
- Go to `File` > `Preferences`
- Add to `Additional boards manager URLs`:
  ```
  https://espressif.github.io/arduino-esp32/package_esp32_index.json
  ```
  
- Navigate to `Tools` > `Board` > `Boards Manager`
- Search for `esp32` by `Espressif Systems`
- select `3.1.0` and above,click the `INSTALL` button to install

3. **Install Required Libraries**
   
  ESP32_Display_Panel and its dependencies are available in Arduino Library Manager. Install online:

  - In Arduino IDE, go to `Sketch` > `Include Library` > `Manage Libraries...`.
  - Search for the `ESP32_Display_Panel` library and select `1.0.3` and above, click the `Install` button to install, you will be prompted whether to install its dependencies, please click `INSTALL ALL` to install all.
  - Install `LVGL` library (optional), recommended version `8.4.0`.

  For manual installation, you can download the required version's `.zip` file from [Github](https://github.com/esp-arduino-libs/ESP32_Display_Panel) or [Arduino Library](https://www.arduinolibraries.info/libraries/esp32_display_panel), then in Arduino IDE navigate to `Sketch` > `Include Library` > `Add .ZIP Library...`, select the downloaded `.zip` file and click `Open` to install.

> [!NOTE]
> * LVGL is only required for GUI examples

4. **Select and configure board**

- Navigate to `Tools` > `Board` > `esp32` > `ESP32S3 Dev Module`

5. **Open example**

- Navigate to `File` > `Examples` > `ESP32_Display_Panel`
- Select `Arduino` > `gui` > `lvgl_v8` > `simple_port`

6. **Modify code**
 
- Modify macros definitions in *esp_panel_board_supported_conf.h* to enable target board.
- Enable file macro definition: #define ESP_PANEL_BOARD_DEFAULT_USE_SUPPORTED       (0) ---> #define ESP_PANEL_BOARD_DEFAULT_USE_SUPPORTED       (1)
- Cancel the comment of the corresponding board:// #define BOARD_VIEWE_SMARTRING ---> #define BOARD_VIEWE_SMARTRING
- here's part of the modified *esp_panel_board_supported_conf.h* file:

    ```c
    ...
    /**
    * @brief Flag to enable supported board configuration (0/1)
    *
    * Set to `1` to enable supported board configuration, `0` to disable
    */
    #define ESP_PANEL_BOARD_DEFAULT_USE_SUPPORTED       (1)
    ...
    #define BOARD_VIEWE_SMARTRING
    // #define BOARD_VIEWE_UEDX24240013_MD50E
    // #define BOARD_VIEWE_UEDX24320024E_WB_A
    // #define BOARD_VIEWE_UEDX24320028E_WB_A
    // #define BOARD_VIEWE_UEDX24320035E_WB_A
    // #define BOARD_VIEWE_UEDX32480035E_WB_A
    // #define BOARD_VIEWE_UEDX46460015_MD50ET
    // #define BOARD_VIEWE_UEDX48270043E_WB_A
    // #define BOARD_VIEWE_UEDX48480021_MD80E_V2
    // #define BOARD_VIEWE_UEDX48480021_MD80E
    // #define BOARD_VIEWE_UEDX48480021_MD80ET
    // #define BOARD_VIEWE_UEDX48480028_MD80ET
    // #define BOARD_VIEWE_UEDX48480040E_WB_A
    // #define BOARD_VIEWE_UEDX80480043E_WB_A
    // #define BOARD_VIEWE_UEDX80480050E_AC_A
    // #define BOARD_VIEWE_UEDX80480050E_WB_A
    // #define BOARD_VIEWE_UEDX80480050E_WB_A_2
    // #define BOARD_VIEWE_UEDX80480070E_WB_A
    ...
    ```

> [!WARNING]
> * Do not enable both `ESP_PANEL_BOARD_DEFAULT_USE_SUPPORTED` and `ESP_PANEL_BOARD_DEFAULT_USE_CUSTOM`
> * You cannot enable multiple boards simultaneously

7. Configure tool options :
    #### ESP32-S3
    | Setting                               | Value                         |
    | :-------------------------------: | :-------------------------------: |
    | Board                                 | ESP32S3 Dev Module            |
    | Core Debug Level                | None                                |
    | USB CDC On Boot                | Disabled                             |
    | USB DFU On Boot                | Disabled                             |
    | Flash Size                           | 16MB (128Mb)                   |
    | Partition Scheme                | 16M Flash (3MB APP/9.9MB FATFS)     |
    | PSRAM                                | OPI PSRAM                      |
   
8. Select the correct port.
9. Click "<kbd>[√](image/8.png)</kbd>" in the upper right corner to compile,If the compilation is correct, connect the microcontroller to the computer,Click "<kbd>[→](image/9.png)</kbd>" in the upper right corner to download.

> [!NOTE]
> LVGL color swap settings,`SPI` and `QSPI` screens need to set the macro of `lv_conf.h` > `LV_COLOR_16_SWAP` to `1` and the `RGB` screen to `0`, as follows :

    ```c
    /**
     * @file lv_conf.h
     * Configuration file for v8.4.0
     */
    
    /* clang-format off */
    #if 1 /*Set it to "1" to enable content*/
    
    #ifndef LV_CONF_H
    #define LV_CONF_H
    
    #include <stdint.h>
    
    /*====================
       COLOR SETTINGS
     *====================*/
    
    /*Color depth: 1 (1 byte per pixel), 8 (RGB332), 16 (RGB565), 32 (ARGB8888)*/
    #define LV_COLOR_DEPTH 16
    
    /*Swap the 2 bytes of RGB565 color. Useful if the display has an 8-bit interface (e.g. SPI)*/
    #define LV_COLOR_16_SWAP 1
    ...
    ```

### firmware download
1. Open the project file "tools" and locate the ESP32 burning tool. Open it.

2. Select the correct burning chip and burning method, then click "OK." As shown in the picture, follow steps 1->2->3->4->5 to burn the program. If the burning is not successful, press and hold the "BOOT-0" button and then download and burn again.

3. Burn the file in the root directory of the project file "[firmware](./firmware/)" file,There is a description of the firmware file version inside, just choose the appropriate version to download.

<p align="center" width="100%">
    <img src="image/10.png" alt="example">
    <img src="image/11.png" alt="example">
</p>

## FAQ

* Q. After reading the above tutorials, I still don't know how to build a programming environment. What should I do?
* A. If you still don't understand how to build an environment after reading the above tutorials, you can refer to the [VIEWE-FAQ]() document instructions to build it.

<br />

* Q. Why does Arduino IDE prompt me to update library files when I open it? Should I update them or not?
* A. Choose not to update library files. Different versions of library files may not be mutually compatible, so it is not recommended to update library files.

<br />

* Q. Why is there no serial data output on the "Uart" interface on my board? Is it defective and unusable?
* A. The default project configuration uses the USB interface as Uart0 serial output for debugging purposes. The "Uart" interface is connected to Uart0, so it won't output any data without configuration.<br />For PlatformIO users, please open the project file "platformio.ini" and modify the option under "build_flags = xxx" from "-D ARDUINO_USB_CDC_ON_BOOT=true" to "-D ARDUINO_USB_CDC_ON_BOOT=false" to enable external "Uart" interface.<br />For Arduino users, open the "Tools" menu and select "USB CDC On Boot: Disabled" to enable the external "Uart" interface.

<br />

* Q. Why is my board continuously failing to download the program?
* A. Please hold down the "BOOT" button and try downloading the program again.

## Schematic
- Please click [here](https://github.com/VIEWESMART/VIEWE-SMARTRING/tree/main/schematic) to download

## Information
Please check the [datasheet](https://github.com/VIEWESMART/VIEWE-SMARTRING/tree/main/datasheet) for relevant data sheets.

## DependentLibraries
* [ESP32_Display_Panel>1.0.1](https://github.com/esp-arduino-libs/ESP32_Display_Panel) (Please [download](./Libraries/ESP32_Display_Panel) the library first as the latest version has not been released yet)
* [ESP32_IO_Expander](https://github.com/esp-arduino-libs/ESP32_IO_Expander) (Please [download](./Libraries/ESP32_IO_Expander) the library first as the latest version has not been released yet)
* [lvgl-8.4.0](https://lvgl.io)




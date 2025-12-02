# 烧录流程说明

[English](https://github.com/VIEWESMART/VIEWE-SMARTRING/blob/main/firmware/README.md)

## 1、打开 ESP32 烧录工具
<img width="892" height="260" alt="image" src="https://github.com/user-attachments/assets/c1f8b64d-d44f-44ce-8f99-ff4d4dac3ba6" />

> [!NOTE]
> * 烧录工具提供在[tools](../tools)文件目录下

## 2、选择正确的芯片和烧录方式
<img width="394" height="372" alt="image" src="https://github.com/user-attachments/assets/e95f3111-2c4a-432f-807e-ebeffa857a79" />

> [!NOTE]
> * 根据自己的芯片选择，此处以ESP32-S3为例子

## 3、进入文件选择和地址配置界面后，进行相应配置，配置完成后记得勾选要烧录的文件
<img width="1107" height="1303" alt="image" src="https://github.com/user-attachments/assets/b2af8b36-213a-49dd-b98f-a1fe130c103d" />

(1)选择烧录文件

(2)填写烧录地址

(3)勾选复选框

(4)配置SPI（一次即可，后续将保持不变）

(5)选择烧录端口和速率（若显烧录失败或检测不到端口请按住boot键后再插数据线，选择端口后松开即可）

(6)开始烧录

> [!NOTE]
> * 一般我们提供的文件为合并文件，所以烧录地址为0x0。若为自己编译产生的通常有三个文件，分别为Bootloader.bin->0x0、partition.bin->0x8000、firmware.bin->0x10000,最有一个文件为自己的项目名,且有可能地址为其他地址请根据编译结果设置

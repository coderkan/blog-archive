# Load Hex file to LPC with JFlash-Lite

Hi everyone,

This chapter will demonstrate you how to load hex file to **LPC** mcu's.  I will use **JFlash-Lite** product of **Jlink** program.

If you are working on Windows OS, open home and search **JFlash Lite** then click it. 

<p align="center">
    <img src="img/arama.png">
</p>

After clicked **JFlash Lite** icon then opened small JFlash Lite GUI. It is easy to use UI. Select **Device** and **Interface** which your connection established for it and **Speed**.

<p align="center">
    <img src="img/program.png">
</p>

Select device in **Device** section and click **OK**.

<p align="center">
    <img src="img/select_mcu.png">
</p>

There are connection interface types that you can select **SWD/JTAG/FINE/2 WIRE JTAG/**.

<p align="center">
    <img src="img/select_interface.png">
</p>

After select all device, interface and speed then click **OK** button and will see main GUI to load hex code. Detailed image as below.

<p align="center">
    <img src="img/open_part.png">
</p>

To load **.hex .axf** etc format files we need to select file and go to path in **Data File** section. 

<p align="center">
    <img src="img/select_hex.png">
</p>

After selected hex file all steps almost finished. If you have finished these steps you can erase chip memory with **Erase Chip** or load hex to device memory with **Program Device** button. 

<p align="center">
    <img src="img/finish_prog.png">
</p>

I hope you enjoy reading.

Have a nice coding.
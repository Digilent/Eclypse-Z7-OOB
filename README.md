Eclypse Z7 Out-of-Box Demo
====================

Description
-----------

This project Is the Out-of-Box demo that is programmed in the QSPI flash of the Eclypse Z7 at manufacturing. Vivado is used to build the demo's hardware platform, and Xilinx SDK is used to program the bitstream onto the board and to build and deploy a C application.

The demo is a simple baremetal application that uses the Zynq processor to control the Eclypse's RGB LEDs and buttons. The LEDs cycle through colors, with intensity brightning and then dimming. Pressing a button turns off the corresponding LED and causes the Zynq processor to print a "Button X Pressed!" message over USB UART.

To receive USB UART messages, use a serial terminal, such as Tera Term, to connect to the Eclypse, with a baud rate of 115200, one start bit, two stop bits, and no parity.

Requirements
------------
* **Eclypse Z7**
* **Vivado 2019.1 Installation with Xilinx SDK**: To set up Vivado, see the [Installing Vivado and Digilent Board Files Tutorial](https://reference.digilentinc.com/vivado/installing-vivado/start).
* **Serial Terminal Application**: 
* **MicroUSB Cable**
* **Power Supply**

Demo Setup
----------

1. Download the most recent release ZIP archive ("Eclypse-Z7-OOB-\*-\*.zip") from the repo's [releases page](https://github.com/Digilent/Eclypse-Z7-OOB/releases).
2. Extract the downloaded ZIP.
3. Launch Vivado 2019.1.
4. Open the XPR project file, found at \<archive extracted location\>/vivado_proj/Eclypse-Z7-OOB.xpr, included in the extracted release archive in Vivado.

FIXME how to reexport changed hardware

5. Launch Xilinx SDK 2019.1. When prompted, set the workspace as \<archive extracted location\>/sdk_workspace.
6. In SDK, click **File -> Import**.
7. In the "Select an import wizard" pane of the window that pops up, expand **General**  and select **Existing Projects into Workspace**. Then click **Next**.
8. **Browse** to \<archive extracted location\>/sdk_workspace, then make sure that all five projects in the directory are selected, click **OK** to import them.
9. Open a serial terminal application (such as TeraTerm) and connect it to the Eclypse Z7's serial port, using a baud rate of 115200.
10. In the toolbar at the top of the SDK window, select **Xilinx -> Program FPGA**. Leave all fields as their defaults and click "Program".
11. In the Project Explorer pane, right click on the "eclypse_z7_oob" application project and select **Run As -> Launch on Hardware (System Debugger)**.
12. The application will now be running on the Eclypse Z7. It can be interacted with as described in the first section of this README.

Next Steps
----------
This demo can be used as a basis for other projects by modifying the hardware platform in the Vivado project's block design or by modifying the SDK application project.

Check out the Eclypse Z7's [Resource Center](https://reference.digilentinc.com/reference/programmable-logic/eclypse-z7/start) to find more documentation, demos, and tutorials.

For technical support or questions, please post on the [Digilent Forum](forum.digilentinc.com).

Additional Notes
----------------
For more information on how this project is version controlled, refer to the [digilent-vivado-scripts repo](https://github.com/digilent/digilent-vivado-scripts).
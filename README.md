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

**Note:** *Vivado projects are version-specific. Some source files are not backward compatible and not automatically forward compatible. Release tags specify the targeted Vivado version. There is only one version targeted per year, as chosen by Digilent. Non-tagged commits on the master branch are either at the last tagged version or the next targeted version (This is not ideal and might be changed in the future).*

**Note:** *Digilent's projects use submodules to bring in libraries. Use the <code>--recursive</code> flag when cloning or <code>git submodule init</code>, if cloned already non-recursively.*

Demo Setup
----------
**Note:** *The steps present in this section detail how the latest tagged release is to be used. Other releases may not use the same flow. Each release archive has its own README placed within it, which contains instructions specific to the version of Vivado targeted by that release.*

1. Download the most recent release ZIP archive ("Eclypse-Z7-OOB-\*-\*.zip") from the repo's [releases page](https://github.com/Digilent/Eclypse-Z7-OOB/releases).
2. Extract the downloaded ZIP.
3. Launch Vivado 2019.1.
4. Open the XPR project file, found at \<archive extracted location\>/vivado_proj/Eclypse-Z7-OOB.xpr, included in the extracted release archive in Vivado.
5. In the menu bar at the top of the window, select **File -> Export -> Export Hardware**. In the resulting pop-up, select a memorable location to place the hardware definition file (the top level of the extracted folder is recommended), then click **OK**.
6. Launch Xilinx SDK 2019.1. When prompted, set the workspace as \<archive extracted location\>/sdk_workspace.
7. In SDK, click **File -> Import**.
8. In the "Select an import wizard" pane of the window that pops up, expand **General** and select **Existing Projects into Workspace**. Then click **Next**.
9. **Browse** to \<archive extracted location\>/sdk_workspace, then make sure that all five projects in the directory are selected, and click **OK** to import them.
10. Right click on the imported hardware platform project (design_1_wrapper_hw_platform_0) and select **Change Hardware Specification**. In the resulting dialog, browse to the folder containing the HDF file, exported from Vivado in step 5, and click **OK**. This will connect the SDK workspace to the hardware definition, such that when any changes are made to the Vivado project later, and the definition is re-exported, SDK will automatically prompt the user to load the new design.
11. Power on the Eclypse Z7 and attach it's USB "PROG" port to the computer via a micro USB cable.
12. Open a serial terminal application (such as TeraTerm) and connect it to the Eclypse Z7's serial port, using a baud rate of 115200.
13. In the toolbar at the top of the SDK window, select **Xilinx -> Program FPGA**. Leave all fields as their defaults and click "Program".
14. In the Project Explorer pane, right click on the "eclypse_z7_oob" application project and select **Run As -> Launch on Hardware (System Debugger)**.
15. The application will now be running on the Eclypse Z7. It can be interacted with as described in the first section of this README.

Next Steps
----------
This demo can be used as a basis for other projects by modifying the hardware platform in the Vivado project's block design or by modifying the SDK application project.

Check out the Eclypse Z7's [Resource Center](https://reference.digilentinc.com/reference/programmable-logic/eclypse-z7/start) to find more documentation, demos, and tutorials.

For technical support or questions, please post on the [Digilent Forum](forum.digilentinc.com).

Additional Notes
----------------
For more information on how this project is version controlled, refer to the [digilent-vivado-scripts](https://github.com/digilent/digilent-vivado-scripts)'s README. 
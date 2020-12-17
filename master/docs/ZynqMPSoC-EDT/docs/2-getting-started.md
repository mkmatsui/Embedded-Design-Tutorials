<p align="right">
            Read this page in other languages:<a href="../docs-jp/2-getting-started.md">日本語</a>    <table style="width:100%"><table style="width:100%">
  <tr>

<th width="100%" colspan="6"><img src="https://www.xilinx.com/content/dam/xilinx/imgs/press/media-kits/corporate/xilinx-logo.png" width="30%"/><h1>Zync UltraScale+ MPSoC Embedded Design Tutorial 2020.2 (UG1209)</h1>
</th>

  </tr>
  <tr>
    <td width="17%" align="center"><a href="../README.md">1. Introduction</a></td>
    <td width="16%" align="center">2. Getting Started</td>
    <td width="17%" align="center"><a href="3-system-configuration.md">3. Zynq UltraScale+ MPSoC System Configuration</a></td>
    <td width="17%" align="center"><a href="4-build-sw-for-ps-subsystems.md">4. Build Software for PS Subsystems</a></td>
</tr>
<tr>
    <td width="17%" align="center"><a href="5-debugging-with-vitis-debugger.md">5. Debugging with the Vitis Debugger</a></td>
    <td width="16%" align="center"><a href="6-boot-and-configuration.md">6. Boot and Configuration</a></td>
    <td width="17%" align="center"><a href="7-system-design-examples.md">7. System Design Examples</a></td>
    <td width="17%" align="center"><a href="8-debugging-problems-with-secure-boot.md">8. Debugging Problems with Secure Boot</a></td>    
  </tr>
</table>

# Getting Started

## Design Files for this Tutorial

The ZIP file associated with this document contains the design files for the tutorial. You can download the <a href="https://www.xilinx.com/cgi-bin/docs/ctdoc?cid=0029d5d7-6dbc-498d-af43-0735c9abfdc4;d=ug1209-embedded-design-tutorial.zip">reference design files</a> from the Xilinx website.

## Hardware Requirements

 This tutorial targets the Zynq UltraScale+ ZCU102 evaluation board.
 The examples in this tutorial were tested using the ZCU102 Rev 1
 board. To use this guide, you need the following hardware items, which
 are included with the evaluation board:

- ZCU102 Rev1 evaluation board

- AC power adapter (12 VDC)

- USB Type-A to USB Micro cable (for UART communications)

- USB Micro cable for programming and debugging via USB-Micro JTAG
     connection

- SD-MMC flash card for Linux booting

- Ethernet cable to connect target board with host machine

- Monitor with DisplayPort (DP) capability and at least 1080P
    resolution.

- DP cable to connect the Display output from ZCU102 Board to a DP
    monitor.

## Installation Requirements

### Vitis Integrated Design Environment and Vivado Design Suite

 Ensure that you have the Vitis 2020.1 software development platform
 installed. The Vitis IDE is a Xilinx unified tool which comes with all
 the hardware and software as a package. If you install the Vitis IDE,
 you will automatically get both the Vivado Design Suite and the Vitis
 IDE. You do not have to make any extra selections in the installer.
 The installation and selection window is shown below.

 ***Note*:** Visit <https://www.xilinx.com/support/download.html to
 confirm that you have the latest tools version.

![](./media/image6.jpeg)

 For more information on installing the Vivado Design Suite, refer to
 the *Vitis Unified Software Platform Documentation: Embedded Software
 Development*
 ([UG1400](https://www.xilinx.com/cgi-bin/docs/rdoc?v=latest%3Bd%3Dug1400-vitis-embedded.pdf)).

### PetaLinux Tools

 Install the PetaLinux tools to run through the Linux portion of this
 tutorial. PetaLinux tools run under the Linux host system running one
 of the following:

- Red Hat Enterprise Workstation/Server 7.4, 7.5, 7.6 (64-bit)

- CentOS Workstation/Server 7.4, 7.5, 7.6 (64-bit)

- Ubuntu Linux Workstation/Server 16.04.5, 16.04.6, 18.04.1, 18.04.02
     (64-bit)

 This can use either a dedicated Linux host system or a virtual machine
 running one of these Linux operating systems on your Windows
 development platform.

 When you install PetaLinux tools on your system of choice, you must do
 the following:

- Download PetaLinux 2020.1 software from the Xilinx website.

- Download the ZCU102 PetaLinux BSP (ZCU102 BSP (prod-silicon)) from
     the 2020.1 downloads page.

- Add common system packages and libraries to the workstation or
     virtual machine. For more information, see the Installation
     Requirements from the *PetaLinux Tools Documentation: Reference
     Guide*
     ([UG1144](https://www.xilinx.com/cgi-bin/docs/rdoc?v=latest%3Bd%3Dug1144-petalinux-tools-reference-guide.pdf)).

#### Prerequisites

- 8 GB RAM (recommended minimum for Xilinx tools)

- 2 GHz CPU clock or equivalent (minimum of eight cores)

- 100 GB free HDD space

#### Extracting the PetaLinux Package

 PetaLinux tools installation is straight-forward. Without any options,
 the PetaLinux tools are installed into the current working directory.
 Alternatively, an installation path may be specified.

 For example, to install PetaLinux tools under
 `/opt/pkg/petalinux/2020.1`:

 For more information, see *PetaLinux Tools Documentation: Reference
 Guide*
 ([UG1144](https://www.xilinx.com/cgi-bin/docs/rdoc?v=latest%3Bd%3Dug1144-petalinux-tools-reference-guide.pdf)).

### Software Licensing

 Xilinx software uses FLEXnet licensing. When the software is first
 run, it performs a license verification process. If the license
 verification does not find a valid license, the license wizard guides
 you through the process of obtaining a license and ensuring that the
 license can be used with the tools installed. If you do not need the
 full version of the software, you can use an evaluation license. For
 installation instructions and information, see the *Vivado Design
 Suite User Guide: Release Notes, Installation, and Licensing*
 ([UG973](https://www.xilinx.com/cgi-bin/docs/rdoc?v=latest%3Bt%3Dvivado%2Binstall%2Bguide)).

### Tutorial Design Files

1. Download the [reference design
     files](https://www.xilinx.com/cgi-bin/docs/ctdoc?cid=0029d5d7-6dbc-498d-af43-0735c9abfdc4%3Bd%3Dug1209-embedded-design-tutorial.zip)
     from the Xilinx website.

2. Extract the ZIP file contents into any write-accessible location.

 To view the contents of the ZIP file, download and extract the
 contents from the ZIP file to C:\\edt. The design files contain the
 XSA files, source code and prebuilt images for all the sections.

 © Copyright 2017-2020 Xilinx, Inc.
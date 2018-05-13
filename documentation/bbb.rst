BBB general information
-----------------------

Some useful links about BBB:

* http://beagleboard.org/boards
* https://beagleboard.org/black
* https://www.elinux.org/Beagleboard:BeagleBoneBlack

BBB serial connector
--------------------

BBB serial connector table:

+---------+----------------------+-------+---------------+
| PIN BBB | Connector USB-Serial | Color | Connector BBB |
+=========+======================+=======+===============+
| 1       | GND                  | Blue  | GND           |
+---------+----------------------+-------+---------------+
| 4       | TX                   | Red   | RX            |
+---------+----------------------+-------+---------------+
| 5       | RX                   | Green | TX            |
+---------+----------------------+-------+---------------+

More USB Serial Cable specs: https://www.olimex.com/Products/Components/Cables/USB-Serial-Cable/USB-Serial-Cable-F/


BBB Linux kernel compilation
----------------------------

Steps to configure and compile the Linux kernel for the BBB:

.. code-block::sh

	# Load OMAP2 configuration for the BBB
	$ make ARCH=arm omap2plus_defconfig

	# Check CONFIG_ROOT_NFS=y with xconfig
	$ make ARCH=arm xconfig

	# Check CONFIG_ROOT_NFS=y with menuconfig
	$ make ARCH=arm menuconfig

	# Compile the Linux kernel
	$ make ARCH=arm CROSS_COMPILE=arm-linux-gnueabi- -j 4

	# Output

The Linux kernel output for this BBB board is located here:
* :sh:`arch/arm/boot/zImage`
* :sh:`arch/arm/boot/dts/am335x-boneblack.dtb`

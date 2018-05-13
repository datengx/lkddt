Setup
-----

Required packages to be installed in your system:

.. code-block:: sh

	$ sudo apt-get install git gitk git-email \
	  picocom \
	  tftpd-hpa \
	  qt5-default g++ pkg-config \
	  libqt4-dev \
	  gcc-arm-linux-gnueabi \
	  nfs-kernel-server


Add your :sh:`$USER` to the :sh:`dialout` group:

.. code-block::sh 

	$ sudo adduser $USER dialout


Remember to logout and login again to confirm changes.

..note::

	Use :sh:`lkddt/scripts/setup` to automatically setup
	your system with required packages and resources


WORKDIR
-------

Creating lkddt WORKDIR to move easily. Choose your own option, here an example:

.. code-block:: sh

	$ export LKDDT=${HOME}/lkddt
	$ cd $LKDDT


Download bootlin data
^^^^^^^^^^^^^^^^^^^^^

Download bootlin resources to have all required resources.

.. code-block:: sh

	$ mkdir -p $LKDDT/rsc/bootlin
	$ cd $LKDDT/rsc/bootlin
	$ wget https://bootlin.com/doc/training/linux-kernel/linux-kernel-slides.pdf
	$ wget https://bootlin.com/doc/training/linux-kernel/linux-kernel-labs.tar.xz
	$ wget https://bootlin.com/doc/training/linux-kernel/linux-kernel-labs.pdf
	$ wget https://bootlin.com/doc/training/linux-kernel/linux-kernel-agenda.pdf
	$ wget https://bootlin.com/doc/training/linux-kernel/linux-kernel-agenda-fr.pdf
	$ wget https://bootlin.com/doc/training/linux-kernel/README.txt
	$ wget https://bootlin.com/labs/doc/nunchuk.pdf
	$ wget https://bootlin.com/labs/doc/README.txt -O README.txt.nunchuk


Download more documentation
^^^^^^^^^^^^^^^^^^^^^^^^^^^

Download Texas Instruments board documentation.

.. code-block:: sh

	$ mkdir -p $LKDDT/rsc/ti
	$ cd $LKDDT/rsc/ti
	$ wget https://github.com/CircuitCo/BeagleBone-Black/raw/master/BBB_SRM.pdf
	$ wget http://www.ti.com/lit/ds/symlink/am3359.pdf
	$ wget http://www.ti.com/lit/ug/spruh73p/spruh73p.pdf


Training setup
^^^^^^^^^^^^^^

Setup training workdir after downloading everything.

.. code-block:: sh

	$ cd $LKDDT/rsc/bootlin
	$ tar xvf linux-kernel-labs.tar.xz -C $LKDDT/

New folder will be created after that: :sh:`$LKDDT/linux-kernel-labs`.


Download Linux kernel source code
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Download Linux kernel mainline source tree and stable releases:

.. code-block:: sh

	$ mkdir -p $LKDDT/linux-kernel-labs/src
	$ cd $LKDDT/linux-kernel-labs/src
	$ git clone git://git.kernel.org/pub/scm/linux/kernel/git/torvalds/linux.git
	$ cd linux/
	$ git remote add stable git://git.kernel.org/pub/scm/linux/kernel/git/stable/linux-stable.git
	$ git fetch stable
	
	# Check available branches
	$ git branch -a


Checkout Linux kernel 4.9 stable version

.. code-block:: sh

	$ cd $LKDDT/linux-kernel-labs/src/linux
	$ git checkout -b 4.9.y stable/linux-4.9.y


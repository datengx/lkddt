cscope
------

Browse source code:

.. code-block::sh

	$ cd $LKDDT/linux-kernel-labs/src/linux
	
	# All files for all architectures at once
	$ cscope -Rk

	# Only files for your current architecture
	$ make cscope
	$ cscope -d cscope.out

More information:
* [Tab]: move the cursor between search results and commands
* [Ctrl] [D]: exit cscope


elixir
------

* https://elixir.bootlin.com/linux/latest/source

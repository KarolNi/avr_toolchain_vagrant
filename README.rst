AVR Toolchain
=============

AVR toolchain, configured using Vagrant. Includes:

- avr gcc
- avr binutils
- avr libc
- avrdude
- make and automake
- git
 
avr gdb is not currently available on Fedora (currently this toolchain is Fedora based).

Getting started
---------------

This is intended to use as submodule in git

1. Install Vagrant https://www.vagrantup.com/ and VM hypervisor https://www.virtualbox.org/
2. In your project directory clone this as submodule (read more about working with submodules here https://git-scm.com/book/en/v2/Git-Tools-Submodules)

.. code-block:: bash

  git submodule add https://github.com/KarolNi/avr_toolchain_vagrant.git

3. get into toolchain

.. code-block:: bash

  cd avr_toolchain_vagrant
  vagrant up; vagrant ssh

Your project will be located in
  /files

4. to stop the toolchain VM
   
.. code-block:: bash

  vagrant halt

5. to free up some disk space when done with project

.. code-block:: bash

  vagrant destroy

Programmers
-----------

Currently USBTiny and USBasp ISPs are configured for passthrough to Vagrant VM. You can add more by modifying Vagrant file using them as example.


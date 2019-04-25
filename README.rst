.. code-block:: none

  > lsb_release -a
  No LSB modules are available.
  Distributor ID:	Ubuntu
  Description:	Ubuntu 18.04.2 LTS
  Release:	18.04
  Codename:	bionic

.. code-block:: none

  > g++ --version
  g++ (Ubuntu 7.3.0-27ubuntu1~18.04) 7.3.0

.. code-block:: none

  rm -rf _builds && cmake -H. -B_builds -DCMAKE_VERBOSE_MAKEFILE=ON
  
.. code-block:: none

  cmake --build _builds

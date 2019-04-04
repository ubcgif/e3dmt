.. _e3dmt_inv:

Inversion Program
=================

There are two options for inversion executables, both of which require parameters set through an :ref:`input file<e3dmt_input_inv>`; denoted here as **e3dMT_octree_inv.inp**. The two executable files are:

    - **e3dMTinv.exe:** Uses the MUMPS direct solver. Faster but larger memory requirements
    - **e3dMTinv_iter.exe:** Uses an iterative solver. Slower run-time but less memory requirements

Running the Program
^^^^^^^^^^^^^^^^^^^

Here, the *mpiexec* call is used to parallelize multiple processes (large-scale independent operations) within the code. To run the executable, open a command window and type the following:

.. figure:: images/run_e3dmt_inv_iter.png
     :align: center
     :width: 700

The call *mpiexec* is followed by the flag *-n*, then the number of processes (*"nFreq"* ) to be carried out simultaneously. This is followed by the paths to the executable and the corresponding input file, respectively. The number of simultaneous processes (*"nFreq"* ) **must** be equal or less than the number of frequencies. Ideally there is enough memory for nFreq to be equal to the number of frequencies.

Setting the Number of Threads with Open MPI
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Before running the executable, the number of threads used to carry out all simultaneous processes can be set with Open MPI. This is set in the command window **before** running the executable. To set the number of threads (*nThreads* ), use the following syntax:

    - Windows computer: "set OMP_NUM_THREADS=nThreads"
    - Linux (bash shell): "export OMP_NUM_THREADS=nThreads"
    - Linux (csh shell): "setenv OMP_NUM_THREADS nThreads"

Units
^^^^^

**Inputs:**

    - **MT data:** Real and imaginary components of impedance tensor entries (V/A)
    - **ZTEM data:** Real and imaginary components of transfer function entries (unitless)
    - **Reference/starting conductivity model:** S/m 
    - **Background susceptibility model:** SI
    - **Model/interface weights:** unitless


.. important:: The current version of the code requires both components for all entries within the impedance tensor. For example, the user cannot invert only the off-diagonal impedance tensor data. Instead the user must supply large uncertainties for the diagonal data.

**Outputs:**

    - **Conductivity model:** S/m


Output Files
^^^^^^^^^^^^

The program **e3dMTinv.exe** creates the following output files:

    - **inv.con:** recovered conductivity models

    - **dpred.txt** predicted data for each recovered conductivity model

    - **e3dMT_octree_inv.log:** log file for the inversion

    - **e3dMT_octree_inv.out:**


.. .. _e3dmt_inv2:

.. Version 2 (2017)
.. ----------------

.. Both the forward and inverse problems are solved using the **e3dMTinv_ver2** executable program. In each case, format of the :ref:`input file<e3dmt_input_inv2>` (denoted here as **e3dMTver2.inp**) is the same. In the case of forward modeling however, some lines in the input file are omitted.

.. Running the Program
.. ^^^^^^^^^^^^^^^^^^^

.. To run the inversion, open a command line window and type the following:

.. .. figure:: images/run_e3dmt_inv2.png
..      :align: center
..      :width: 700

.. The *mpiexec* call is used for parallelization. This is followed by the flag *-n*, then the number of frequencies (*"nFreq"*). This is followed by the inversion executable and the corresponding input file.

.. Units
.. ^^^^^

.. **Input and outputs:**

..     - **MT data:** Real and imaginary components of impedance tensor entries (V/A)
..     - **ZTEM data:** Real and imaginary components of transfer function entries (unitless)
..     - **Conductivity model:** S/m
..     - **Reference/starting conductivity model:** S/m 
..     - **Background susceptibility model:** SI
..     - **Model/interface weights:** unitless


.. .. important::

..     - The current version of the code cannot forward model or invert both MT and ZTEM data, just one or the other.
..     - If a flag value of -99 is used as the uncertainty for a particular datum, the inversion will omit that datum. Using this, we are not required to invert all entries of the impedance tensor or transfer function.


.. Output Files
.. ^^^^^^^^^^^^

.. The program **e3dMTinv_ver2.exe** creates the following output files:

..     - **inv.con:** recovered conductivity models

..     - **dpred.txt** predicted data for each recovered conductivity model

..     - **e3dMTinv.log:** log file for the inversion

..     - **e3dMTinv.out:**






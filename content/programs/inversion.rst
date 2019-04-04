.. _e3dmt_inv:

Inversion Program
=================

Both the forward and inverse problems are solved using the **e3dMTinv_ver2** executable program. In each case, format of the :ref:`input file<e3dmt_input_inv2>` (denoted here as **e3dMTver2.inp**) is the same. In the case of forward modeling however, some lines in the input file are omitted.

Running the Program
^^^^^^^^^^^^^^^^^^^

Here, the *mpiexec* call is used to parallelize multiple processes (large-scale independent operations) within the code. To run the executable, open a command window and type the following:

.. figure:: images/run_e3dmt_inv2.png
     :align: center
     :width: 700

The call *mpiexec* is followed by the flag *-n*, then the number of processes (*"nFreq"* ) to be carried out simultaneously. This is followed by the paths to the executable and the corresponding input file, respectively. The number of simultaneous processes (*"nFreq"* ) **must** be equal or less than the number of frequencies. Ideally there is enough memory for *nFreq* to be equal to the number of frequencies.

Setting Number of Threads with Open MPI
^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^

Before running the executable, the number of threads used to carry out all simultaneous processes can be set with Open MPI. This is set in the command window **before** running the executable. To set the number of threads (*nThreads* ), use the following syntax:

    - Windows computer: "set OMP_NUM_THREADS=nThreads"
    - Linux (bash shell): "export OMP_NUM_THREADS=nThreads"
    - Linux (csh shell): "setenv OMP_NUM_THREADS nThreads"

.. important:: The number of processes (*nFreq* ) times the number of threads (*nThreads* ) **cannot** exceed the total number of threads available from the computer.

Units
^^^^^

**Input and outputs:**

    - **MT data:** Real and imaginary components of impedance tensor entries (V/A)
    - **ZTEM data:** Real and imaginary components of transfer function entries (unitless)
    - **Conductivity model:** S/m
    - **Reference/starting conductivity model:** S/m 
    - **Background susceptibility model:** SI
    - **Model/interface weights:** unitless


Output Files
^^^^^^^^^^^^

The program **e3dMTinv_ver2.exe** creates the following output files:

    - **inv.con:** recovered conductivity models

    - **dpred.txt** predicted data for each recovered conductivity model

    - **e3dMTinv.log:** log file for the inversion

    - **e3dMTinv.out:**






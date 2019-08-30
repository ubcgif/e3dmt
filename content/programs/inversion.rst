.. _e3dmt_inv:

Inversion Program
=================

There are two options for inversion executables, both of which require parameters set through an :ref:`input file<e3dmt_input_inv>`; denoted here as **e3dmt.inp**. The two executable files are:

    - **e3dmt.exe:** Uses the MUMPS direct solver. Faster but larger memory requirements
    - **e3dmt_iter.exe:** Uses an iterative solver. Slower run-time but less memory requirements

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

    - **e3dmt.log:** log file for the inversion

    - **e3dmt.out:**




.. _e3dmt_fwd:

Forward Modeling Program
========================

The forward problem is solved using the executable program **e3dmt_fwd.exe**. Parameters necessary for running the forward modeling code are set in the :ref:`input file<e3dmt_input_fwd>`; denoted here as **e3dmtfwd.inp**.

Running the Program
^^^^^^^^^^^^^^^^^^^

To run the forward modeling program, open a command line window. Type the path to the code **e3dmt_fwd.exe**, followed by a space, followed by the path to the :ref:`input file<e3dmt_input_fwd>`.

.. figure:: images/run_e3dmt_fwd.png
     :align: center
     :width: 600


Units:
^^^^^^

**Inputs:**

    - **Conductivity model:** S/m
    - **Background susceptibility model:** SI

**Outputs:**

    - **MT data:** Real and imaginary components of impedance tensor entries (V/A)
    - **ZTEM data:** Real and imaginary components of transfer function entries (unitless)


.. _e3dmt_fwd_output:

Output Files
^^^^^^^^^^^^

The program **e3dmt_fwd.exe** creates 2 output files:

    - **MT_data.txt:** data predicted using the conductivity model provided

    - **e3dmt.log:** log file



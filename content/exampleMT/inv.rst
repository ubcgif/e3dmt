.. _exampleMT_inv:

Inversion
=========

Here, the code **e3dmt.exe** and the input file **e3dmt.inp** (:ref:`see format <e3dmt_input_inv>`) are used to invert MT data. MT data were created in the example ":ref:`forward modeling<exampleMT_fwd>`". Uncertainties of 0.001 V/A +/- 5\% were added to all off diagonal impedance tensor elements. Uncertainties of 0.0005 V/A +/- 5\% were added to all diagonal impedance tensor elements. In practice, data are noisy and choosing appropriate uncertainties is very important for successful inversion. Files relevant to this part of the example are in the sub-folder *inv*. Before running this example, you may want to do the following:

	- `Download and open the zip folder containing the entire E3DMT version 1 example <https://github.com/ubcgif/e3dmt/raw/e3dmt/assets/e3dmt_v1_example_MT.zip>`__ (if not done already)
	- :ref:`Learn how to run code from command line <e3dmt_inv>`
	- :ref:`Learn the format of the input file <e3dmt_input_inv>`

To invert the synthetic data, the input file below was used:

.. figure:: ../inputfiles/images/create_inv_input.png
     :align: center
     :width: 700


The true model (left) and recovered model (right) are shown below. A cutoff of 0.1 S/m has been used for both models and the recovered model is transected horizontally at z = -500 m. 

.. figure:: images/inv1.png
     :align: center
     :width: 700

.. _example_inv:

Inversion
=========

Here, the code **e3dmt_v2.exe** and the input file **e3dmt.inp** (:ref:`see format<e3dmt_input_inv>`) are used to invert MT data. MT data were created in the example :ref:`forward modeling<example_fwd>`. Uncertainties of 0.001 V/A +/- 5\% were added to all off-diagonal impedance tensor elements. Uncertainties of 0.0005 V/A +/- 5\% were added to all diagonal impedance tensor elements. In practice, data are noisy and choosing appropriate uncertainties is very important for successful inversion. Files relevant to this part of the example are in the sub-folder *inv_final*. Before running this example, you may want to do the following:

	- `Download and open the zip folder containing the entire E3DMT version 2 example <https://github.com/ubcgif/e3dmt/raw/e3dmt_v2/assets/e3dmt_v2_example_MT.zip>`__ (if not done already)
	- Learn how to :ref:`run code from command line<e3dmt_inv>`
	- Learn the :ref:`format of the input file<e3dmt_input_inv>`

To invert the synthetic data, the following input file was used:


.. figure:: ../inputfiles/images/inv_input_ver2.png
     :align: center
     :width: 700

The true model (left) and recovered model (right) at iteration 6 are shown below. A cutoff of 0.05 S/m has been used for both models and the recovered model is transected at z = -1200 m. In examining recovered models, this iteration accurately explained the data without fitting the noise and recovered the block.

.. figure:: images/inv2.png
     :align: center
     :width: 700







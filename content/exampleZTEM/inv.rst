.. _exampleZTEM_inv:

Inversion
=========

Here, the code **e3dmt_v2.exe** and the input file **e3dmt.inp** (:ref:`see format<e3dmt_input_inv>`) are used to invert ZTEM data. ZTEM data were created in the example :ref:`forward modeling<exampleZTEM_fwd>`. Uncertainties of 0.01 V/A +/- 5\% were added to tipper data at 10 Hz and 50 Hz. Uncertainties of 0.005 V/A +/- 5\% were added to tipper data at 200 Hz. In practice, data are noisy and choosing appropriate uncertainties is very important for successful inversion. Files relevant to this part of the example are in the sub-folder *inv*. Before running this example, you may want to do the following:

	- `Download and open the zip folder containing the entire E3DMT version 2 example <https://github.com/ubcgif/e3dmt/raw/e3dmt_v2/assets/e3dmt_v2_example_ZTEM.zip>`__ (if not done already)
	- Learn how to :ref:`run code from command line<e3dmt_inv>`
	- Learn the :ref:`format of the input file<e3dmt_input_inv>`

To invert the synthetic data, the following input file was used:


.. figure:: ./images/input.png
     :align: center
     :width: 700

The true model (left) and recovered model (right) are shown below. A cutoff of 0.1 S/m has been used for both models and the recovered model is transected at z = -400 m.

.. figure:: images/inv2.png
     :align: center
     :width: 700







.. _boundsFile:

Model File
==========

For a given mesh, the bounds file has the following 2 column format:


|
| :math:`L_1 \;\; U_1`
| :math:`L_2 \;\; U_2`
| :math:`\; \vdots \;\;\;\;\;\; \vdots`
| :math:`L_N \;\; U_N`
|
|

where :math:`L_i` refers to a lower bound value in S/m for cell :math:`i` and :math:`U_i` refers to an upper bound value.

.. note:: Bounds provided for inactive cells, including the air, do not play a role in the solution and so they can be assigned any number.









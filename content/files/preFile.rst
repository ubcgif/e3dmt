.. _preFile:

Predicted Data File
===================

Predicted data files output by **e3dMTinv_ver2.exe** contain the locations and predicted data. The ordering (rows) of the data correspond to the rows in the :ref:`index file <indexFile>`. For plotting purposes, the predicted data are defined at a single point; despite the fact that raw fields are measured with a set of receivers. This point depends on the locations of the receivers at for each measurement location and is different for MT and ZTEM data.


MT data (DATATYPE MT)
^^^^^^^^^^^^^^^^^^^^^

Each row in the array contains the elements of the impedance tensor, defined at a particular location and separated into real and imaginary components. The units for predicted MT data are (V/A). The rows for this data format are as follows:

.. math::
    | \; Easting \; | \; Northing \; | \; Elevation \; | \; Z^\prime_{xx} \; | \; Z^{\prime \prime}_{xx} \; | \; Z^\prime_{xy} \; | \; Z^{\prime \prime}_{xy} \; | \; Z^\prime_{yx} \; | \; Z^{\prime \prime}_{yx} \; | \; Z^\prime_{yy} \; | \; Z^{\prime \prime}_{yy} \; |

where

    - The locations are Easting, Northing and elevation in metres
    - :math:`Z^\prime_{ij}` is the real component of entry i,j of the impedance tensor
    - :math:`Z^{\prime\prime}_{ij}` is the imaginary component of entry i,j of the impedance tensor

.. important::

    - For standard MT data, X = Northing, Y = Easting and Z = Down; which this code uses! Thus :math:`Z_{xy}` is essentially the ratio of the electric field along the Northing and the magnetic field along the Easting. For more, see the :ref:`theory section<theory_nsem>`.
    - The location of the data point is the average of the node locations defining the Hy receiver. Thus if the same Hy receiver is used for several measurements, the data will be plotted in the same location.


ZTEM data (DATATYPE ZTEM)
^^^^^^^^^^^^^^^^^^^^^^^^^

Each row in the array contains the elements of the transfer function, defined at a particular location and separated into real and imaginary components. Predicted ZTEM data are unitless with no normalization factor. The rows for this data format are as follows:

.. math::
    | \; Easting \; | \; Northing \; | \; Elevation \; | \; T^\prime_{zx} \; | \; T^{\prime \prime}_{zx} \; | \; T^\prime_{zy} \; | \; T^{\prime \prime}_{zy} \; |

where

    - The locations are Easting, Northing and elevation in metres
    - :math:`T^\prime_{zx}` is the real component of :math:`T_{zx}`
    - :math:`T^{\prime\prime}_{zx}` is the imaginary component of :math:`T_{zx}`

and similarly for :math:`T_{zy}`.

.. important::

    - For standard natural source data, X = Northing, Y = Easting and Z = Down; which this code uses! Thus :math:`T_{zx}` is the transfer function related to an incident plane wave whose electric field is polarized along the Northing direction; which produces magnetic fields with components in the Easting direction. For more, see the :ref:`theory section<theory_nsem>`.
    - The location of the data point is the average of the node locations defining the Hz receiver. Thus if the same Hz receiver is used for several measurements, the data will be plotted in the same location.














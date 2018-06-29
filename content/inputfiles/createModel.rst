.. _e3dmt_input_model:

Create Model Input File
=======================

.. note:: Although separate executables were designed for each version of the code, the input and output file formats are the same. As a result, the approach for creating models using either package is acceptable.

Version 1 (2014 and 2015)
-------------------------

.. _e3dmt_blk3cell_input:

Input File for blk3cell
^^^^^^^^^^^^^^^^^^^^^^^

The input file defines the properties of the model (conductivity/susceptibility/active) created using **blk3cell.exe**. The user specifies the locations, dimensions and values for a set of blocks. All undefined cells within the mesh are set to the background value. The format for this file is as follows:

.. tabularcolumns:: |C|C|C|

+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| Line #         | Parameter                                                                                                 | Description                            |
+================+===========================================================================================================+========================================+
| 1              |:math:`\sigma_b`                                                                                           | background conductivity/susceptibility |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| 2              |:math:`N`                                                                                                  | number of blocks                       |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| 3              |:math:`x_1^{(1)} \;\;  x_2^{(1)} \;\; y_1^{(1)} \;\; y_2^{(1)} \;\; z_1^{(1)} \;\; z_2^{(1)} \;\; m^{(1)}` | Block 1                                |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| 4              |:math:`x_1^{(2)} \;\;  x_2^{(2)} \;\; y_1^{(2)} \;\; y_2^{(2)} \;\; z_1^{(2)} \;\; z_2^{(2)} \;\; m^{(2)}` | Block 2                                |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| :math:`\vdots` |:math:`\vdots`                                                                                             | :math:`\vdots`                         |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+                                
|                |:math:`x_1^{(N)} \;\;  x_2^{(N)} \;\; y_1^{(N)} \;\; y_2^{(N)} \;\; z_1^{(N)} \;\; z_2^{(N)} \;\; m^{(N)}` | Block N                                |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+

where superscript :math:`(i)` for :math:`i=1,2,...,N` refers to a particular block. :math:`x_1,x_2,y_1,y_2,z_1` and :math:`z_2` define the nodes of each block and :math:`m` defines conductivity/susceptibility value. An example is shown below.


.. figure:: images/create_blk3cell_input.png
     :align: center
     :width: 700

     Example input file for blk3cell (`Download <https://github.com/ubcgif/e3dmt/raw/master/assets/input_files1/blk3cell.inp>`__ )


.. _e3dmt_3Dmodel2octree_input:

Input File for Model2Octree
^^^^^^^^^^^^^^^^^^^^^^^^^^^

The file **Model2Octree.inp** contains the paths to the tensor mesh (**3D_mesh.txt**), tensor model (**3Dmodel.con**) and octree mesh (**octree_mesh.txt**) as well as other necessary parameters. The format of the input file is as follows:

.. tabularcolumns:: |C|C|C|

+--------+----------------------------------+-------------------------------------------------------------------------------------------------------------+
| Line # | Parameter                        | Description                                                                                                 |
+========+==================================+=============================================================================================================+
| 1      | :math:`Model \; Type`            | Either *LIN_MODEL* or *LOG_MODEL*                                                                           |
+--------+----------------------------------+-------------------------------------------------------------------------------------------------------------+
| 2      | :math:`Octree \; mesh`           | File path to Octree mesh                                                                                    |
+--------+----------------------------------+-------------------------------------------------------------------------------------------------------------+
| 3      | :math:`Tensor \; mesh`           | File path to tensor mesh                                                                                    |
+--------+----------------------------------+-------------------------------------------------------------------------------------------------------------+
| 4      | :math:`Tensor \; model`          | 3D model on tensor mesh                                                                                     |
+--------+----------------------------------+-------------------------------------------------------------------------------------------------------------+
| 5      | :math:`Output \; mesh \; name`   | Name for re-meshed Octree mesh or enter *USE_INPUT_MESH*                                                    |
+--------+----------------------------------+-------------------------------------------------------------------------------------------------------------+
| 6      | :math:`Output \; model \; name`  | File name for conductivity model on Octree mesh                                                             |
+--------+----------------------------------+-------------------------------------------------------------------------------------------------------------+
| 7      | :math:`Start \; point`           | Either :ref:`START_LARGE_CELLS<e3dmt_input_octreeln9>` or :ref:`START_SMALL_CELLS<e3dmt_input_octreeln9>`   |
+--------+----------------------------------+-------------------------------------------------------------------------------------------------------------+

.. note::

     Consider the following with regards to **line 5**:
          - The edges of structures defined within the underlying tensor mesh may bisect larger cells within the Octree mesh. If an output name is provided, the program will output a new Octree mesh with refined cells such that the edges of structures do not bisect cells. Thus the input and output Octree mesh may have a different number of cells.
          - If *USE_INPUT_MESH* is entered, the model on the underlying tensor mesh is interpolated onto the pre-existing Octree mesh.


An example input file and the resulting conductivity model on the octree mesh are shown below

.. figure:: images/create_3DtoOctree_input.png
     :align: center
     :width: 700

     Example input file for 3DModel2Octree.exe (`Download <https://github.com/ubcgif/e3dmt/raw/master/assets/input_files1/3Dmodel2octree.inp>`__ )


Version 2 (2017)
----------------

The file **blk3cellOct.inp** defines the model (conductivity/susceptibility/active). The user specifies the locations, dimensions and values for a set of blocks. All undefined cells within the mesh are set to the background value. The format for this file is as follows:

.. tabularcolumns:: |C|C|C|

+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| Line #         | Parameter                                                                                                 | Description                            |
+================+===========================================================================================================+========================================+
| 1              | *Octree Mesh*                                                                                             | path to octree mesh                    |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| 2              | *Out Model Name*                                                                                          | output model name                      |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| 3              |:math:`\sigma_b`                                                                                           | background conductivity/susceptibility |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| 4              |:math:`N`                                                                                                  | number of blocks                       |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| 5              |:math:`x_1^{(1)} \;\;  x_2^{(1)} \;\; y_1^{(1)} \;\; y_2^{(1)} \;\; z_1^{(1)} \;\; z_2^{(1)} \;\; m^{(1)}` | Block 1                                |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| 6              |:math:`x_1^{(2)} \;\;  x_2^{(2)} \;\; y_1^{(2)} \;\; y_2^{(2)} \;\; z_1^{(2)} \;\; z_2^{(2)} \;\; m^{(2)}` | Block 2                                |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+
| :math:`\vdots` |:math:`\vdots`                                                                                             | :math:`\vdots`                         |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+                                
|                |:math:`x_1^{(N)} \;\;  x_2^{(N)} \;\; y_1^{(N)} \;\; y_2^{(N)} \;\; z_1^{(N)} \;\; z_2^{(N)} \;\; m^{(N)}` | Block N                                |
+----------------+-----------------------------------------------------------------------------------------------------------+----------------------------------------+

where superscript :math:`(i)` for :math:`i=1,2,...,N` refers to a particular block. :math:`x_1,x_2,y_1,y_2,z_1` and :math:`z_2` define the nodes of each block and :math:`m` defines conductivity/susceptibility value.






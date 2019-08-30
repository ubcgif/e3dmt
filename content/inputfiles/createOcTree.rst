.. _e3dmt_input_octree:

Create OcTree Mesh Input File
=============================

.. _e3dmt_input_octree2:

:ref:`OcTree meshes<octreeFile>` used in the E3DMT code are created using the program **create_octree_mesh_e3dmt_v2.exe**. Parameters necessary for defining the OcTree mesh are set in the input file. The lines of input file are as follows:

.. tabularcolumns:: |C|C|C|

+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| Line # | Parameter                                                                                                                                                     | Description                                                               |
+========+===============================================================================================================================================================+===========================================================================+
| 1      |:ref:`dx dy dz<e3dmt_input_octree2ln1>`                                                                                                                        | minimum cell widths in x, y and z for the mesh                            |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 2      |:ref:`min_cell_fact<e3dmt_input_octree2ln2a>` :math:`\;` :ref:`min_cell_size<e3dmt_input_octree2ln2b>` :math:`\;` :ref:`max_topo_cell<e3dmt_input_octree2ln2c>`| controls discretization based on padding, topography and receivers        |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 3      |:ref:`x_pad y_pad down_pad up_pad<e3dmt_input_octree2ln3>`                                                                                                     | sets extent of mesh in x, y and z                                         |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 4      |:ref:`dist_1 dist_2 dist_3 ... dist_n <e3dmt_input_octree2ln4>`                                                                                                | sets discretization in core region                                        |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 5      |:ref:`n1 n2 n3<e3dmt_input_octree2ln5>`                                                                                                                        | sets the thicknesses of layers of finest discretization near the receivers|
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 6a     |:ref:`dataFile<e3dmt_input_octree2ln6>`                                                                                                                        | path to observations file                                                 |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 6b     |:ref:`receiverFile<e3dmt_input_octree2ln7>`                                                                                                                    | path to receivers file                                                    |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 6c     |:ref:`frequencyFile<e3dmt_input_octree2ln8>`                                                                                                                   | path to frequencies file                                                  |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 7      |:ref:`topoFile<e3dmt_input_octree2ln9>`                                                                                                                        | sets topography                                                           |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 8      |:ref:`shift_data<e3dmt_input_octree2ln10>`                                                                                                                     | *description needed. leave as NOT_SHIFT_DATA*                             |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 9      |    :ref:`MAKE_POLYGON D<e3dmt_input_octree2ln11>`                                                                                                             | sets lateral extent of core region                                        |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+
| 10     |    :ref:`CREATE_LARGE_MESH out_name<e3dmt_input_octree2ln12>`                                                                                                 | name of output mesh                                                       |
+--------+---------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------+



.. figure:: images/create_octree_input_ver2.png
     :align: center
     :width: 700

     Example input file for creating octree mesh (`Download <https://github.com/ubcgif/e3dmt/raw/e3dmt_v2/assets/input_files_ver2/octree_mesh.inp>`__ )


Line Descriptions
^^^^^^^^^^^^^^^^^


.. _e3dmt_input_octree2ln1:

    - **dx dy dz:** Minimum cell widths in x, y and z for the mesh.

.. _e3dmt_input_octree2ln2a:

    - **min_cell_fact:** Used to scale the cell values of :ref:`dist_1 dist_2 dist_3 ... dist_n <e3dmt_input_octree2ln4>` outside the survey region. Allows the user to reduce the level of discretization of surface topography outside the survey region. For relatively flat topography, this value has little bearing on the final mesh; *DEFAULT = 1*. Must be a power of 2.

.. _e3dmt_input_octree2ln2b:

    - **min_cell_size:** For ground-based surveys, this value is redundant; leave as 1. For airborne ZTEM, we may want to specify the cell size between the surface topography and the fine cells around the receivers (:ref:`n1 n2 n3<e3dmt_input_octree2ln5>`). Here, *min_cell_size* is a factor defining the size of these cells relative to the underlying mesh cell size (:ref:`dx dy dz<e3dmt_input_octree2ln1>`). *max_topo_cell* is an integer value equal or greater than 1 and must be a power of 2. *DEFAULT = 1*.

.. _e3dmt_input_octree2ln2c:

    - **max_topo_cell:** Far from the core region (padding cells), the user may want to prevent overly large cells from defining the topography. Here, *max_topo_cell* is a factor defining the maximum cell size relative to the underlying mesh cell size (:ref:`dx dy dz<e3dmt_input_octree2ln1>`) that can be used along the surface topography. *max_topo_cell* is an integer value equal or greater than 1 and must be a power of 2.

.. _e3dmt_input_octree2ln3:

    - **x_pad y_pad down_pad up_pad:** Distance from the data boundary in the x, y, downward and upward directions, respectively, that the mesh extends. True padding in the octree mesh may be larger since cell sizes must increase by factors of 2.

.. _e3dmt_input_octree2ln4:

    - **dist_1 dist_2 dist_3 ... dist_n:** Sets the distance from surface topography and receivers in which the cells widths are increased by a factor of 2 in x, y and z. Up to a depth of *dist_1* from surface topography, the smallest cell size is used (set by *dx, dy, dz*). For the following *dist_2* metres, the cell widths are doubled. For the following *dist_3* metres, the cell widths are doubled again. The user can enter an unlimited number of core mesh layers. Outside a depth and horizontal distance of *dist_1+dist_2+dist_3+...+dist_n*, the cells widths increase by a factor of 2 for every additional layer (see the figure below).

.. _e3dmt_input_octree2ln5:

    - **n1 n2 n3:** This sets the thicknesses of layers of finest discretization near the receivers. **n1 = 4** means that around each receiver, there is a layer 4 cells thick that uses the finest discretization. This is followed by a layer which is **n2** cells thick, where the cell dimensions are increased by a factor of 2. Likewise for the 3rd layer.

.. _e3dmt_input_octree2ln6:

    - **dataFile:** E3DMT version 2 can accept observation files written in two different formats (E3DMT version 1 or version 2).

    	- If version 1 file formats are being used, enter the flag *V1FORMAT* followed by the path to a :ref:`version 1 formatted data file <obsFile1>`
    	- If version 2 file formats are being used, simply enter the path to a :ref:`version 2 formatted data file <obsFile2>` 

.. _e3dmt_input_octree2ln7:

    - **receiverFile:** file path to the receiver file 

    	- If version 1 file formats are being used, this line does not exist in the input file
    	- If version 2 file formats are being used, provide the path to the :ref:`receiver file <receiverFile>`

.. _e3dmt_input_octree2ln8:

    - **frequencyFile:** The file path to the frequencies file

    	- If version 1 file formats are being used, this line does not exist in the input file
    	- If version 2 file formats are being used, provide the path to the :ref:`frequencies file<freqFile>`.

.. _e3dmt_input_octree2ln9:

    - **topoFile:** There are three options for defining surface topography

    	- Enter the file path to a :ref:`topography file<topoFile>`
    	- For flat topography, enter "TOPO_CONST" followed by a space then the elevation of the surface topography; for example "TOPO_CONST 125.5"
    	- The user may also use the flag "NO_TOPO" to have all cells lie below the surface. For practical applications, this is **not** recommended

.. _e3dmt_input_octree2ln10:

    - **shift_data:**

    	- If the flag *NOT_SHIFT_DATA* is used, survey locations are preserved when creating the OcTree mesh
    	- The user may also use the flag *SHIFT_DATA* followed by an output file name. If any of the receivers lie below the surface topography, the program will project those receivers to the surface and output a new survey file containing the new receiver locations.

.. _e3dmt_input_octree2ln11:

    - **MAKE_POLYGON D:** The horizontal area covered by the core region is determined by the locations of the receivers and the value of *D* in metres. Essentially, the code creates a convex hull from all the points defining the receivers. It then extends the convex hull by a distance *D*. On this line, the user enters *MAKE_POLYGON* followed by the value *D*.

.. _e3dmt_input_octree2ln12:

    - **CREATE_LARGE_MESH out_name:** Here the user enters the flag *CREATE_LARGE_MESH* followed by the output name for the octree mesh.












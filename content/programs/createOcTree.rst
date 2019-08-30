.. _e3dmt_octree:

Create OcTree Mesh
==================


:ref:`OcTree meshes<octreeFile>` used in the E3DMT version 1 code are created using the program **create_octree_mesh_e3dmt.exe**. Parameters necessary for defining the OcTree mesh are set in the :ref:`input file<e3dmt_input_octree>`; referred to here as **octree_mesh.inp**.

To generate the OcTree mesh, open a command window. Type the path to the code **create_octree_mesh_e3dmt.exe**, followed by a space, followed by the path to the input file.

.. figure:: images/run_create_octree_mesh.png
     :align: center
     :width: 700



.. _e3dmt_octree_output:


The program **create_octree_mesh_e3dmt.exe** creates 5 output files:

    - **3D_mesh.txt:** the underlying regular :ref:`tensor mesh<tensorFile>`. This mesh is comprised of the smallest cell size and is very large (>> 1M cells). As a result, it is unwise to plot this mesh.

    - **3D_core_mesh.txt:** A 3D regular :ref:`tensor mesh<tensorFile>` defining the core region. 

    - **octree_mesh.txt:** :ref:`OcTree mesh<octreeFile>` used in the forward modeling and inversion codes

    - **active_cells.txt:** :ref:`active cells model<modelFile>` on the OcTree mesh. Cells are active if assigned a value of 1 and inactive if assigned a value of 0 

    - **create_mesh.log:** log file




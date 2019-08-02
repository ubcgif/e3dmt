.. _e3dmt_octree:

Create OcTree Mesh
==================

:ref:`OcTree meshes<octreeFile>` used in the E3DMT version 2 code are created using the program **create_octree_mesh_e3dmt_v2.exe**. Parameters necessary for defining the OcTree mesh are set in the :ref:`input file<e3dmt_input_octree2>`; referred to here as **MTcreate_mesh.inp**.

To generate an OcTree mesh, open a command window. Type the path to the code **create_octree_mesh_e3dmt_v2.exe**, followed by a space, followed by the path to the input file.

.. figure:: images/run_create_octree_mesh2.png
     :align: center
     :width: 500


.. _e3dmt_octree2_output:


The program **create_octree_mesh_e3dmt_v2.exe** creates 5 output files:

    - **3D_mesh.txt:** the underlying regular tensor mesh. This mesh is comprised of the smallest cell size and is very large (>> 1M cells). As a result, it is unwise to plot this mesh.

    - **3D_core_mesh.txt:** A 3D regular tensor defining the core region. 

    - **octree_mesh.txt:** :ref:`OcTree mesh<octreeFile>` used in the forward modeling and inversion codes

    - **active_cells_topo.txt:** :ref:`active cells model<modelFile>` on the OcTree mesh. Cells are active if assigned a value of 1 and inactive if assigned a value of 0 

    - **create_octree_mesh_e3dmt_v2.log:** log file











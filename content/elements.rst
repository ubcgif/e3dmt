.. _elements:

Elements of the Program E3DMT
=============================

This section provides a description of each program in the E3DMT libraries.

Version 1 (2014 and 2015)
-------------------------

.. important:: Although described here, this generation of the code will not be supported by GIFtools in the future.

Version 1 of the E3DMT codes contains the following executables:

    - **MTcreate_octree_mesh_e3d:** creates an octree mesh around the receiver array
    - **e3dMTfwd:** Solves the forward problem. Computes the electric and magnetic response to a 3D conductivity model (fields, and impedance)
    - **e3dMTinv:** Solves the inverse problem using a direct solver approach. Recovers a conductivity model by inverting MT or ZTEM data. All entries of the impedance tensor or transfer function are needed.
    - **e3dMTinv_iter:** Solves the inverse problem using an iterative solver approach. Recovers a conductivity model by inverting MT or ZTEM data. All entries of the impedance tensor or transfer function are needed.


Version 2 (2017)
----------------

.. important:: This generation of the E3DMT code is meant to be maintained longterm.

Version 2 of the E3DMT codes contains the following executables:


Octree Utilities
----------------

The following Octree utility programs may be useful:

    - **blk3cell:** Creates models from a set of blocks
    - **3DModel2Octree:** Converts models from tensor to Octree meshes
    - **interface_weights:** Creates interface weights

General Files for E3DMT Executables
-----------------------------------

Here, we describe the formats of supplementary files used to run E3DMT executable files. The input files for each executable program are described in the :ref:`running the programs<running>` section.

.. toctree::
    :maxdepth: 1

    Survey and Locations File <files/surveyFile>
    Receiver File <files/receiverFile>
    Locations Index File <files/indexFile>
    Predicted Data File <files/preFile>
    Observations File <files/obsFile>
    Topography File <files/topoFile>
    Tensor Mesh File <files/tensor_mesh>
    Octree Mesh File <files/octree_mesh>
    Model File <files/model>
    Model and Face Weights Files <files/weights>













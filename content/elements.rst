.. _elements:

Elements of the Program E3DMT
=============================

This section provides a brief description of each program in the E3DMT version 2 library. In addition, we describe the file formats for all input and supporting files used by the coding library.

Executables
-----------

The main executable programs within the E3DMT version 2 program library are:

    - **e3dmt_v2:** Is used for both forward modeling and inverting natural source electromagnetic data
    - **create_octree_mesh_e3dmt_v2:** Creates the OcTree mesh from survey geometry

Mesh utilities that can be used in conjunction with this package include:

    - **blk3cellOct:** Creates simple block conductivity models on the OcTree mesh
    - **interface_weights:** Creates interface weights for inversion

Main Input Files
----------------

Here, we describe the main input files for executables contained with the E3DMT version 2 package.

.. toctree::
    :maxdepth: 2

    Create octree mesh <inputfiles/createOcTree>
    Create octree model <inputfiles/createModel>
    Forward modeling <inputfiles/forward>
    Create face weights <inputfiles/weightsFiles>
    Inversion <inputfiles/inversion>


Supporting Files
----------------

Here, we describe the formats of supporting files used to run E3DMT executable files. The input files for each executable program are described in the :ref:`running the programs<running>` section.

.. toctree::
    :maxdepth: 1

    Survey Index File <files/indexFile>
    Receiver File <files/receiverFile>
    Frequencies Files <files/freqFile>
    Predicted Data File <files/preFile>
    Observations File <files/obsFile>
    Topography File <files/topoFile>
    Octree Mesh File <files/octree_mesh>
    Model File <files/model>
    Model and Face Weights Files <files/weights>
    Bounds File <files/bounds>













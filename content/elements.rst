.. _elements:

Elements of the Program E3DMT
=============================

This section provides a brief description of each program in the E3DMT version 1 library. In addition, we describe the file formats for all input and supporting files used by the coding library.

Executables
-----------

.. important:: Although described here, this generation of the code may not be supported by GIFtools in the future.

The main executable programs within the E3DMT version 1 program library are:

    - **e3dmt_fwd:** Solves the forward problem. Computes the electric and magnetic response to a 3D conductivity model (fields, and impedance)
    - **e3dmt:** Solves the inverse problem using a direct solver approach (MUMPS). Recovers a conductivity model by inverting MT or ZTEM data. All entries of the impedance tensor or transfer function are needed.
    - **e3dmt_iter:** Solves the inverse problem using an iterative solver approach. Recovers a conductivity model by inverting MT or ZTEM data. All entries of the impedance tensor or transfer function are needed.
    - **create_octree_mesh_e3dmt:** Creates an octree mesh based on the :ref:`survey file<surveyFile>`

Common Octree utility programs used with this package include:

    - **blk3cell:** Creates models from a set of blocks on a tensor mesh
    - **3DModel2Octree:** Converts models from tensor to Octree meshes
    - **interface_weights:** Creates interface weights


Main Input Files
----------------

Here, we describe the main input files for executables contained with the E3DMT version 1 package.

.. toctree::
    :maxdepth: 1

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

    Survey and Locations File <files/surveyFile>
    Predicted Data File <files/preFile>
    Observations File <files/obsFile>
    Topography File <files/topoFile>
    Tensor Mesh File <files/tensor_mesh>
    Octree Mesh File <files/octree_mesh>
    Model File <files/model>
    Model and Face Weights Files <files/weights>













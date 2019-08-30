.. _running:

Running the programs
====================

This section provides describes how to run all executables pertaining to the E3DMT version 1 package.

.. note::

    All executable files, input files, output filenames and files specified within input files can be specified in the following manner:

    - as just the filename if contained within the current working directory (Example: *filename.txt*)
    - as a file path relative to the current working directory (Example: *sub_dir\\filename.txt*)
    - as the full path (Example: *C:\\Users\\Name\\Tests\\filename.txt*)

    Executable files should **not** be renamed. However, input file names can be specified by the user if desired.

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


Contents
--------

To learn the specifics of running each executable, see the following sections:

  .. toctree::
    :maxdepth: 1

    OcTree Mesh Generation <programs/createOcTree>
    Creating Octree Models <programs/createModel>
    Forward Modeling <programs/forward>
    Additional Cell and Face Weights <programs/weightsFiles>
    Inversion <programs/inversion>


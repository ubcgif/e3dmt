.. _running:

Running the programs
====================

This section provides describes how to run all executables pertaining to the E3DMT version 2 (2017) package.

.. note::

    All executable files, input files, output filenames and files specified within input files can be specified in the following manner:

    - as just the filename if contained within the current working directory (Example: *filename.txt*)
    - as a file path relative to the current working directory (Example: *sub_dir\\filename.txt*)
    - as the full path (Example: *C:\\Users\\Name\\Tests\\filename.txt*)

    Executable files should **not** be renamed. However, input file names can be specified by the user if desired.


Executables
-----------

The main executable programs within the E3DMT version 2 program library are:

    - **e3dmt_v2:** Is used for both forward modeling and inverting natural source electromagnetic data
    - **create_octree_mesh_e3dmt_v2:** Creates the OcTree mesh from survey geometry

Mesh utilities that can be used in conjunction with this package include:

    - **blk3cellOct:** Creates simple block conductivity models on the OcTree mesh
    - **interface_weights:** Creates interface weights for inversion


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


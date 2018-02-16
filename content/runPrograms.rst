Running the programs
====================

The software package E3DMT contains the following Fortran executable codes:

- ``MTcreate_octree_mesh_e3d``: Creates OcTree mesh


.. note::

	All executable files, input files, output filenames and files specified within input files can be specified in the following manner:

	- as just the filename if contained within the current working directory (Example: *filename.txt*)
	- as a file path relative to the current working directory (Example: *sub_dir\\filename.txt*)
	- as the full path (Example: *C:\\Users\\Name\\Tests\\filename.txt*)

	Executable files should **not** be renamed. However, input file names can be specified by the user if desired.




Input and output files
----------------------

  .. toctree::
    :maxdepth: 1

    OcTree Mesh Generation <programs/createOcTree>
    Create Models <programs/createModel>
    Forward Modeling (e3dMTfwd.inp) <programs/forward>
    Inversion (e3dMTinv.exe) <programs/inversion>


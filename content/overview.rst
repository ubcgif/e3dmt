.. _overview:

E3DMT version 1 package overview
================================

Description
-----------

This manual provides instructions and background information for the E3DMT version 1 program library.
This library is capable of forward modeling and inverting magnetotelluric and ZTEM data. E3DMT is built in the same
manner as E3D, so much of the background presented in this manual is identical to the E3D manual.
In order to decrease computational time and increase accuracy by mesh refinement in areas of
interest, conductivity models are discretized on an Octree mesh. 


.. figure:: images/OcTree.png
     :align: center
     :width: 700

     2D (QuadTree) mesh discretization about a ring (left). Cell refinement for OcTree mesh (right).


The program library has utilities for generating OcTree meshes and conductivity models.
From the users point of view the software operates in much the same way as previous GIF codes. Both codes can be run from the command line or through the GIFtools GUI.

Both program libraries provide codes to do the following:

   1. Create OcTree meshes based on the survey geometry

   2. Construct models on OcTree meshes, where each cell is assigned a constant value of conductivity.

   3. Forward model magnetotelluric and ZTEM data resulting from a particular conductivity model.

   4. Invert surface (MT), airborne (ZTEM) data to generate 3D conductivity models:
   
      - The inversion is solved as an optimization problem with the simultaneous goals of (i) minimizing an objective function dependent on the model and (ii) generating synthetic data that match observations to within a degree of misfit consistent with the statistics of those data.
      - To counteract the inherent lack of information, the formulation incorporates reference model and smoothing by regularization.
      - Capacity for the user to directionally weight smoothing and reference model influence as well as overall influence of regularization on objective function minimization. Explicit prior information may also take the form of upper and lower bounds on the conductivity contrast in any cell.
      - The regularization parameter (controlling relative importance of objective function and misfit terms).


The initial research underlying the E3DMT version 1 (2014) library was funded principally by the mineral industry consortium \Joint and Cooperative Inversion of Geophysical and Geological Data" (1991 -
1997) which was sponsored by NSERC and the following 11 companies: BHP Minerals, CRA Exploration, Cominco Exploration, Falconbridge, Hudson Bay Exploration and Development, INCO
Exploration & Technical Services, Kennecott Exploration Company, Newmont Gold Company,
Noranda Exploration, Placer Dome, and WMC.

Since then, improvements have been implemented as time and resources permit.

Program Library Content
-----------------------

The main executable programs within the E3DMT version 1 (2014) program library are:

    - **MTcreate_octree_mesh_e3d:** Creates the OcTree used in forward simulations and inversions from survey data.
    - **blk3cell:** Creates simple conductivity models on a core tensor mesh
    - **3DModel2Octree:** Converts 3D conductivity on core mesh to OcTree mesh
    - **e3dMTfwd:** Performs the forward simulation
    - **e3dMTinv and e3dmtinv_iter:** Inverts observed data in order to recover a conductivity model

Also included are the following Octree utility programs:

      - create weight file
      - face weights
      - octree cell centre
      - octreeTo3D
      - refine octree


Licensing
---------

Licensing for commercial use is managed by distributors, not by the UBC-GIF research group.


Installation
------------

E3DMT Executables
^^^^^^^^^^^^^^^^^

There is no automatic installer currently available for E3DMT version 1. Please follow the following steps in order to use the software:

   1. Extract all files provided from the given zip-based archive and place them all together in a new folder.
   2. Add this directory as new path to your environment variables.
   3. Make sure to create a separate directory for each new inversion, where all the associated files will be stored. Do not store anything in the bin directory other than executable applications and Graphical User Interface applications (GUIs).

MPI Executables
^^^^^^^^^^^^^^^

Message passaging interface (MPI) programming allows E3DMT version 1 to utilize parallel computing. Even if the code is being run on a single machine, the user is **required** to download the necessary MPI package to use the E3DMT version 1 executables. To set up MPI:

    1. Download and install:
    	
    	- `Microsoft MPI v10.0 <https://www.microsoft.com/en-us/download/details.aspx?id=57467>`__ : Required for window machines
    	- `MPICH <https://www.mpich.org/downloads/>`__ : Required for Linux machines
    	- `Open MPI v4 <https://www.open-mpi.org/software/ompi/v4.0/>`__ : Optional programming to set MPI threads

    2. Path the folders containing MPI executables to your environment variables.







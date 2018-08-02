.. _overview:

E3DMT package overview
======================

Description
-----------

This manual provides instructions and background information for the E3DMT version 2 program library (2017).
The library is capable of forward modeling and inverting magnetotelluric and ZTEM data. E3DMT version is is built in the same
manner as AEM, so much of the background presented in this manual is identical to the AEM manual.
In order to decrease computational time and increase accuracy by mesh refinement in areas of
interest, conductivity models are discretized on an Octree mesh. 


.. figure:: images/OcTree.png
     :align: center
     :width: 700

     2D (QuadTree) mesh discretization about a ring (left). Cell refinement for OcTree mesh (right).


The E3DMT version 2 program library has utilities for generating OcTree meshes and conductivity models.
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


The E3DMT version 2 (2017) program library was developed under the IRC consortium.

Since then, improvements have been implemented as time and resources permit.

.. E3DMT version 1 (2014) Program Library Content
.. ----------------------------------------------

.. The main executable programs within the E3DMT version 1 (2014) program library are:

..     - **MTcreate_octree_mesh_e3d:** Creates the OcTree used in forward simulations and inversions from survey data.
..     - **blk3cell:** Creates simple conductivity models on a core tensor mesh
..     - **3DModel2Octree:** Converts 3D conductivity on core mesh to OcTree mesh
..     - **e3dMTfwd:** Performs the forward simulation
..     - **e3dMTinv and e3dmtinv_iter:** Inverts observed data in order to recover a conductivity model

.. Also included are the following Octree utility programs:

..       - create weight file
..       - face weights
..       - octree cell centre
..       - octreeTo3D
..       - refine octree


E3DMT version 2 (2017) Program Library Content
----------------------------------------------

The main executable programs within the E3DMT version 2 (2017) program library are:

    - **octree_mesh_mt:** Creates the OcTree used in forward simulations and inversions from survey data
    - **blk3cellOct:** Creates simple block conductivity models on the OcTree mesh
    - **e3dMTinv_ver2:** Is used for both forward modeling and inverting natural source electromagnetic data




Licensing
---------

Licensing for commercial use is managed by distributors, not by the UBC-GIF research group.


Installing E3DMT
----------------

There is no automatic installer currently available for the e3dMT. Please follow the following steps in order to use the software:

   1. Extract all files provided from the given zip-based archive and place them all together in a new folder.
   2. Add this directory as new path to your environment variables.
   3. If you are running the software on a cluster of computers, please install the Message Pass Interface (MPI) on your computer and add it to your path in addition from
   4. Make sure to create a separate directory for each new inversion, where all the associated files will be stored. Do not store anything in the bin directory other than executable applications and Graphical User Interface applications (GUIs).







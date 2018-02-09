.. _elements:

Elements of the Program E3DMT
=============================

Introduction
------------

This section provides a description of each program in the E3DMT library.

	1. E3DMT Executable programs:
		- MTcreate octree mesh e3d: creates an octree mesh around the receiver array
		- e3dMTfwd: Forward Problem: computes the electric and magnetic response to a 3D conductivity model (fields, and impedance)
		- e3dMTinv: Inverse Problem: computes a conductivity model by inverting MT or ZTEM data.

	2. Octree utilities:
		- create weight file: creates the weighting on each cell in the model
		- face weights: creates interface weights on the faces of cells
		- octree cell centre: computes the cell centres of each octree cell
		- octreeTo3D: converts an octree mesh to a 3D base mesh
		- refine octree: refine the octrees
		- re-mesh octree model: converts the octree model to a new octree mesh

General Files for E3DMT Executables
-----------------------------------

Here, we describe the formats of files used to run E3DMT executable files.


.. toctree::
    :maxdepth: 1

    Data File <files/dataFile>
    Topography File <files/topoFile>













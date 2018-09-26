# snappy_with_AMR
Modification of the [OpenFOAM](https://openfoam.org/)'s tutorial case [windAroundBuildings](https://github.com/OpenFOAM/OpenFOAM-6/tree/master/tutorials/incompressible/simpleFoam/windAroundBuildings) that makes use of dynamic mesh refinement on the mesh that was created by snappyHexMesh. In addition, the case was modified by run with the transient solver [pimpleFoam](https://github.com/OpenFOAM/OpenFOAM-6/blob/master/applications/solvers/incompressible/pimpleFoam/pimpleFoam.C) by default.

Relevant changes to allow the use of dynamicRefineFvMesh on a snappyHexMesh-generated mesh:

- Add "constant/dynamicFvMeshDict"
- In "system/snappyHexMeshDict": enable the "scalarLevels" flag in the list "writeFlags"
- Modify "Allrun" to automate the necessary copy and re-formatting of "cellLevel" and "pointLevel" files
- Replace "simpleFoam" by a solver with dynamic mesh capabilities e.g. "pimpleFoam" (changes in "system/controlDict" & "system/fvSolution")

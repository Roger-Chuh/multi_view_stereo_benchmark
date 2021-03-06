# Dependencies of the multi view stereo benchmark

This folder contains code for 3d reconstruction algorithms and their dependencies.

## A note on the level of build integration
Dependencies are git submodules, so that the versions of our dependencies are tracked in the parent repository.

Sources for dependencies that are part of Ubuntu 14.04, i.e. boost, python,
etc... are NOT included in the repo, but should be noted in the documentation
for each package to ease installation.

CMake will be the primary build tool for this project, since it is what most of
our dependencies are using.  HOWEVER, CMake is... not great from a language
design standpoint; everything gets thrown into a global namespace, making
reliable composition of projects impossible.  Therefore, we do NOT attempt to
integrate the builds of all the dependencies into one CMake invocation, and
rely instead on some other mechanism to make building everything easier. 

See the ../bootstrap.sh script

We may be quite liberal in how we hack on the CMakeLists files of our
dependencies to make them easier to configure and run.


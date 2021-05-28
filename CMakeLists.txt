#----------------------------------------------------------------------------
# Setup the project
cmake_minimum_required(VERSION 2.6 FATAL_ERROR)
project(geant4tiny)

#----------------------------------------------------------------------------
# Find Geant4 package, activating all available UI and Vis drivers by default
# You can set WITH_GEANT4_UIVIS to OFF via the command line or ccmake/cmake-gui
# to build a batch mode only executable
find_package(Geant4 REQUIRED ui_all vis_all) ## very important

#----------------------------------------------------------------------------
# Add the executable, and link it to the Geant4 libraries
#
add_executable(geant4tiny geant4tiny.cc)
target_link_libraries(geant4tiny ${Geant4_LIBRARIES}) ## very very necessary
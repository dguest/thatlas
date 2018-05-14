##################################################################
# Package level things
##################################################################
#

# Set the name of the package:
atlas_subdir( dumpxAOD )

# Packages that this package depends on
atlas_depends_on_subdirs(
  PRIVATE
  Control/xAODRootAccess
  Event/xAOD/xAODJet)

# External(s) used by the package:
find_package(ROOT REQUIRED COMPONENTS RIO Hist Tree Net Core)

# common requirements
set(_common
  Root/JetWriter.cxx
  INCLUDE_DIRS ${ROOT_INCLUDE_DIRS}
  LINK_LIBRARIES ${ROOT_LIBRARIES}
  xAODRootAccess
  xAODJet)

# Build the test executable:
atlas_add_executable( dump-xaod util/dump-xaod.cxx ${_common} )

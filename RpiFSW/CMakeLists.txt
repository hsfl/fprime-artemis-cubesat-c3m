#####
# 'RpiFSW' Deployment:
#
# This registers the 'RpiFSW' deployment to the build system. 
# Custom components that have not been added at the project-level should be added to 
# the list below.
#
#####

restrict_platforms(Linux)

set(CMAKE_CXX_STANDARD 17)

###
# Topology and Components
###
add_fprime_subdirectory("${CMAKE_CURRENT_LIST_DIR}/Top/")

# Add custom components to this specific deployment here
add_fprime_subdirectory("${CMAKE_CURRENT_LIST_DIR}/Camera/")

set(SOURCE_FILES "${CMAKE_CURRENT_LIST_DIR}/Main.cpp")
set(MOD_DEPS 
    ${FPRIME_CURRENT_MODULE}/Top 
)

register_fprime_deployment()
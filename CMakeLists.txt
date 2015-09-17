project( NIST_VASIR )
cmake_minimum_required( VERSION 2.8 )

set( BUILD_EXAMPLE OFF CACHE BOOL "Build YooIRIS example program")

add_subdirectory( MasekAlg )
add_subdirectory( Analysis )
add_subdirectory( VASIR )
if ( BUILD_EXAMPLE )
  add_subdirectory( YooIRIS )
endif()

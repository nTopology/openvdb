
add_subdirectory("thirdparty/Half")
add_subdirectory("openvdb")

if(WIN32)
  add_subdirectory("thirdparty/tbb")
  # Passing up variables
  set(TBB_DLLS ${TBB_DLLS} PARENT_SCOPE)
endif()


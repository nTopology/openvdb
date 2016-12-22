
add_subdirectory("thirdparty/tbb")
add_subdirectory("thirdparty/Half")
add_subdirectory("openvdb")

# Passing up variables
set(TBB_DLLS ${TBB_DLLS} PARENT_SCOPE)

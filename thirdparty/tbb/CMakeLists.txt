# tbb

add_library ( tbb INTERFACE )

target_include_directories(tbb INTERFACE include)

target_link_libraries(tbb INTERFACE
  debug ${CMAKE_CURRENT_SOURCE_DIR}/lib/intel64/vc14/tbb.lib
  optimized ${CMAKE_CURRENT_SOURCE_DIR}/lib/intel64/vc14/tbb.lib)

list(APPEND dlls
  ${CMAKE_CURRENT_SOURCE_DIR}/bin/intel64/vc14/tbb.dll
  ${CMAKE_CURRENT_SOURCE_DIR}/bin/intel64/vc14/tbb_debug.dll
)

set(TBB_DLLS ${dlls} PARENT_SCOPE)

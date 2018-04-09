# openvdb

if(WIN32)
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /wd4800")
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /wd4146")
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /wd4244")
  set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /wd4267")
endif()


list (APPEND sources
  Grid.h
  Grid.cc
  MetaMap.h
  MetaMap.cc
  Metadata.h
  Metadata.cc
  Platform.h
  PlatformConfig.h
  io/Archive.h
  io/Archive.cc
  io/Compression.h
  io/Compression.cc
  io/File.h
  io/File.cc
  io/GridDescriptor.h
  io/GridDescriptor.cc
  io/Queue.h
  io/Queue.cc
  io/Stream.h
  io/Stream.cc
  io/TempFile.h
  io/TempFile.cc
  math/Maps.h
  math/Maps.cc
  math/Proximity.h
  math/Proximity.cc
  math/QuantizedUnitVec.h
  math/QuantizedUnitVec.cc
  math/Transform.h
  math/Transform.cc
  points/AttributeArray.h
  points/AttributeArray.cc
  points/AttributeArrayString.h
  points/AttributeArrayString.cc
  points/AttributeGroup.h
  points/AttributeGroup.cc
  points/AttributeSet.h
  points/AttributeSet.cc
  points/StreamCompression.h
  points/StreamCompression.cc
  points/points.cc
  openvdb.h
  openvdb.cc
  util/Formats.h
  util/Formats.cc
  util/Util.h
  util/Util.cc
)

source_group("" FILES ${sources})

add_library (openvdb STATIC ${sources})

target_include_directories(openvdb PUBLIC ..)

target_compile_definitions(openvdb PUBLIC OPENVDB_STATICLIB OPENVDB_OPENEXR_STATICLIB) #OPENVDB_USE_BLOSC OPENVDB_PRIVATE
target_compile_definitions(openvdb PUBLIC NOMINMAX)

target_link_libraries ( openvdb PUBLIC
  boost
  #${PYTHON_LIBRARY}
  tbb
  half
  zlibstatic
)

# half

add_library ( half STATIC
  OpenEXR/toFloat.h
  OpenEXR/eLut.h
  OpenEXR/half.cpp
  OpenEXR/half.h
  OpenEXR/halfExport.h
  OpenEXR/halfFunction.h
  OpenEXR/halfLimits.h
)

target_include_directories(half INTERFACE .)

if(UNIX) 
 target_compile_options(half PUBLIC -Wno-register)
endif()


project(cmake_wrapper)

include("${CMAKE_BINARY_DIR}/conanbuildinfo.cmake")
conan_basic_setup()

if(MSVC)
  if(MSVC_VERSION AND MSVC_VERSION GREATER_EQUAL 1910)
    add_definitions(-DGTEST_LANG_CXX11=1 -DGTEST_HAS_TR1_TUPLE=0)
  endif(MSVC_VERSION AND MSVC_VERSION GREATER_EQUAL 1910)
endif(MSVC)

add_subdirectory("source_subfolder")

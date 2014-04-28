project(pvr.dvbviewer)

cmake_minimum_required(VERSION 2.6)

enable_language(CXX)

find_package(TinyXML REQUIRED)
find_package(xbmc REQUIRED)
find_package(xbmcplatform REQUIRED)

include_directories(${xbmcplatform_INCLUDE_DIRS}
                    ${XBMC_INCLUDE_DIR}
                    ${TINYXML_INCLUDE_DIRS})

add_definitions(-D__STDC_FORMAT_MACROS)

set(DVBVIEWER_SOURCES src/client.cpp
                      src/DvbData.cpp
                      src/TimeshiftBuffer.cpp)

set(DEPLIBS ${xbmcplatform_LIBRARIES} ${TINYXML_LIBRARIES})

build_addon(pvr.dvbviewer DVBVIEWER DEPLIBS)

include(CPack)

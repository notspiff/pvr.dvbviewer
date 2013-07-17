PROJECT(pvr.dvbviewer)

CMAKE_MINIMUM_REQUIRED(VERSION 2.6)

ENABLE_LANGUAGE(CXX)

FIND_PACKAGE(xbmc REQUIRED)
FIND_PACKAGE(xbmcplatform REQUIRED)

addon_version(pvr.dvbviewer DVBVIEWER)

INCLUDE_DIRECTORIES(${xbmcplatform_INCLUDE_DIRS}
                    ${XBMC_INCLUDE_DIR})

ADD_DEFINITIONS(-D__STDC_FORMAT_MACROS)

SET(SOURCES src/client.cpp
            src/DvbData.cpp
            src/TimeshiftBuffer.cpp
            src/xmlParser.cpp)

SET(DEPLIBS ${xbmcplatform_LIBRARIES})

build_addon(pvr.dvbviewer SOURCES DEPLIBS DVBVIEWER_VERSION)
install_addon(pvr.dvbviewer ${DVBVIEWER_VERSION})

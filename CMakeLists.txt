cmake_minimum_required(VERSION 2.8)  
PROJECT(myreactorserver)  
AUX_SOURCE_DIRECTORY(./ SRC_LIST)
SET(EXECUTABLE_OUTPUT_PATH ./)  
ADD_DEFINITIONS(-g -W -Wall -Wno-deprecated
                -DLINUX -D_REENTRANT -D_FILE_OFFSET_BITS=64
                -DAC_HAS_INFO -DAC_HAS_WARNING -DAC_HAS_ERROR 
                -DAC_HAS_CRITICAL -DTIXML_USE_STL
                -DHAVE_CXX_STDHEADERS ${CMAKE_CXX_FLAGS}
                -std=c++11)  
INCLUDE_DIRECTORIES(  ./  )
#LINK_DIRECTORIES(./)  
set(  main.cpp  myreator.cpp  logger.cpp)  
ADD_EXECUTABLE(myreactorserver ${SRC_LIST})  
TARGET_LINK_LIBRARIES(myreactorserver pthread)  
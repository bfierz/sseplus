CMAKE_MINIMUM_REQUIRED(VERSION 3.1.0)

PROJECT(SSEPlus CXX)

# Define header only library
ADD_LIBRARY(sseplus INTERFACE)
TARGET_INCLUDE_DIRECTORIES(sseplus INTERFACE
    $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}>
)

OPTION(SSEPLUS_TEST "Generate tests." OFF)
IF (SSEPLUS_TEST)
	ADD_EXECUTABLE(C_Sanity
		SSEPlus_Test/C_Sanity/main.c
	)

	ADD_EXECUTABLE(UnitTest
		SSEPlus_Test/UnitTest/src/main.cpp
	)
ENDIF()

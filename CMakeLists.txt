# See the NOTICE file
# distributed with this work for additional information
# regarding copyright ownership.  The ASF licenses this file
# to you under the Apache License, Version 2.0 (the
# "License"); you may not use this file except in compliance
# with the License.  You may obtain a copy of the License at
#
#   http://www.apache.org/licenses/LICENSE-2.0
#
# Unless required by applicable law or agreed to in writing,
# software distributed under the License is distributed on an
# "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
# KIND, either express or implied.  See the License for the
# specific language governing permissions and limitations
# under the License.


cmake_minimum_required(VERSION 3.0 FATAL_ERROR)
project(importer)


set (Importer_VERSION_MAJOR 1)
set (Importer_VERSION_MINOR 0)
 
# configure a header file to pass some of the CMake settings
# to the source code
configure_file (
  "${PROJECT_SOURCE_DIR}/src/importer.h.in"
  "${PROJECT_BINARY_DIR}/importer.h"
  )
 
# add the binary tree to the search path for include files
# so that we will find TutorialConfig.h
include_directories("${PROJECT_BINARY_DIR}")
 
# add the executable
add_executable(importer src/importer.cc)
target_link_libraries (importer parquet arrow)


#SET(sampleName MyApp)
# In the above line we declared a variable sampleName and assigned it a value MyApp. We will make use of the same later.project(PrjMyApp)
# here we define the project or solution (for visual studio) name
# In following lines we try to find out the packages of additional libraries, if reqd. Here we are trying to locate PCL and mrpt library.
# u may replace the names by yours. Each such package should have a Cmake file in them, if not then we may have to manually define the paths.
# we Show that later.
#find_package(parquet REQUIRED)


# here we specify the additional include directories for the project. These files come in additional include directories option of VC++
# project.
# either the variable values from package like ${PCL_INCLUDE_DIRS} or absolute paths as shown in second and third line may be used.
#include_directories(${PCL_INCLUDE_DIRS})
#include_directories("G:/Matlab/extern/include")
#include_directories("C:/Program Files/MobileRobots/Aria/include")

# here we specify the additional library directories for the linker in the project. These files come in additional library directories
# option of VC++ project.
# either the variable values from package like ${PCL_LIBRARY_DIRS} or absolute paths as shown in second and third line may be used.
# An update, link_directories is being pulled out, you may use TARGET_LINK_LIBRARIES instead as shown below
#link_directories(${PCL_LIBRARY_DIRS})
#link_directories("G:/Matlab/extern/lib/win32/microsoft")
#link_directories("C:/Program Files/MobileRobots/Aria/lib")

# here we add definitions for any package if requred.
#add_definitions(${PCL_DEFINITIONS})

# The following line is very important.
# It specifies the executable name. Here the executable is the first parameter i.e. MyApp and a file MyApp.exe will be created on
# compilation in windows platform.
# Followed by the executable name come all your source and header files.
# All cpp fles will be clubbed into source folder and all .h files will be added to header files folder of the project.
#add_executable (MyApp Local.cpp part.h grab.h interface.h test.cpp test.h)

# There may be some additional dependencies which you may have to specify for the project, which you may do as in following lines.
# Note that first parameter is the executable name.
#target_link_libraries (MyApp ${PCL_LIBRARIES} libeng.lib libmx.lib libmex.lib libmat.lib Aria.lib winmm.lib wsock32.lib)
# Add the required libraries for linking:
#TARGET_LINK_LIBRARIES(${sampleName}
#${MRPT_LIBS} # This is filled by FIND_PACKAGE(MRPT ...)
#"" # Optional extra libs...
#)


#add_subdirectory(src)


# End of CMakeLists.Txt file. Save it as a plain text file and the name 

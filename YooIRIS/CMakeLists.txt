project( YooIRIS )
cmake_minimum_required( VERSION 2.8.11 )

find_package( OpenCV REQUIRED )
message(STATUS "OpenCV_INCLUDE_DIRS : ${OpenCV_INCLUDE_DIRS}")
message(STATUS "OpenCV_LIBS : ${OpenCV_LIBS}")
find_package( Qt5Widgets REQUIRED )

include_directories (
	${CMAKE_CURRENT_LIST_DIR}/../Analysis
	${CMAKE_CURRENT_LIST_DIR}/../MasekAlg
	${CMAKE_CURRENT_LIST_DIR}/../VASIR
	${Qt5Widgets_INCLUDE_DIRS}
	${OpenCV_INCLUDE_DIRS}
)

set(CMAKE_INCLUDE_CURRENT_DIR ON)
set(CMAKE_AUTOMOC ON)

set( CMAKE_CXX_FLAGS  "${CMAKE_CXX_FLAGS} -fPIC" )

set ( YooIRIS_HDRS
	CVImageSource.h
	ImageSource.h
	ImageWidget.h
	InputDialog.h
	ModeDialog.h
	YooIRIS.h
)

set ( YooIRIS_SRCS
	CVImageSource.cpp
	ImageWidget.cpp
	InputDialog.cpp
	main.cpp
	ModeDialog.cpp
	YooIRIS.cpp
	YooUtility.cpp
)

qt5_wrap_ui( YooIRIS_UI
	ModeDialog.ui
	YooIRIS.ui
	InputDialog.ui
)

add_executable ( YooIRIS ${YooIRIS_SRCS} ${YooIRIS_HDRS} ${YooIRIS_UI} )
target_link_libraries ( YooIRIS VASIR MasekAlg Analysis Qt5::Widgets ${OpenCV_LIBS} )

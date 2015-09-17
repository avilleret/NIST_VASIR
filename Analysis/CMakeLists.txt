project( Analysis )
cmake_minimum_required( VERSION 2.8 )

find_package ( OpenCV REQUIRED )

include_directories (
	${CMAKE_CURRENT_LIST_DIR}/../MasekAlg
	${CMAKE_CURRENT_LIST_DIR}/../VASIR
)

set ( Analysis_HDRS
	Analysis.h
	GetROC.h
	Utility.h
)

set ( Analysis_SRCS
	AnScores.cpp
	GetROC.cpp
	Utility.cpp
)

add_library ( Analysis SHARED ${Analysis_SRCS} ${Analysis_HDRS} )

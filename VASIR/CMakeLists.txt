project( VASIR )
cmake_minimum_required( VERSION 2.8 )

find_library( OpenCV REQUIRED )

include_directories (
	${CMAKE_CURRENT_LIST_DIR}/../MasekAlg
)

set ( VASIR_HDRS
				AlignLRPupilPos.h
				CreateTemplate.h
				EncodeLee.h
				EyeDetection.h
				EyeRegionExtraction.h
				FindEyelidCurve.h
				FindHighLights.h
				FindIrisCircle.h
				FindPupilCircleNew.h
				GetHammingDistance.h
				ImageQuality.h
				ImageUtility.h
				MasekLee.h
				MatchAlg.h
				MatchingTemplate.h
				Normalization.h
				Shifts.h
)

set ( VASIR_SRCS
			  AlignLRPupilPos.cpp
				CreateTemplate.cpp
				EdgeDensity.cpp
				EncodeLee.cpp
				EyeDetection.cpp
				EyeRegionExtraction.cpp
				FindEyelidCurve.cpp
				FindHighLights.cpp
				FindIrisCircle.cpp
				FindPupilCircleNew.cpp
				FindTwoPupilCircles.cpp
				GaborConvolve.cpp
				GetHammingDistance.cpp
				ImageQuality.cpp
				ImageUtility.cpp
				MatchAlg.cpp
				MatchingTemplate.cpp
				Normalization.cpp
				Shifts.cpp
			  MasekLee.cpp
)

add_library ( VASIR SHARED ${VASIR_SRCS} ${VASIR_HDRS} )

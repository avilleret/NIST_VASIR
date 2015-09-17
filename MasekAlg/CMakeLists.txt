project( MasekAlg )
cmake_minimum_required( VERSION 2.8 )

set ( MasekAlg_HDRS
        Masek.h
        global.h
        imread.h
)

set ( MasekAlg_SRCS
        adjgamma.cpp
        canny.cpp
        circlecoordinates.cpp
        createiristemplate.cpp
        encode.cpp
        findcircle.cpp
        findline.cpp
        gaborconvolve.cpp
        gauss.cpp
        gethammingdistance.cpp
        houcircle.cpp
        hysthresh.cpp
        imread.cpp
        imwrite.cpp
        interp2.cpp
        linecoords.cpp
        mymat.cpp
        nonmaxsup.cpp
        normalizeiris.cpp
        radon.cpp
        saveiristemplate.cpp
        segmentiris.cpp
        shiftbits.cpp
        utility.cpp
)

add_library ( MasekAlg SHARED ${MasekAlg_SRCS} ${MasekAlg_HDRS} )
target_link_libraries ( MasekAlg )

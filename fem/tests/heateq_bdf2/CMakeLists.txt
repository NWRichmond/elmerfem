INCLUDE(test_macros)
INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/fem/src)

CONFIGURE_FILE( TempDist.sif TempDist.sif COPYONLY)

file(COPY ELMERSOLVER_STARTINFO angle.grd DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/")

ADD_ELMER_TEST(heateq_bdf2)
ADD_ELMER_LABEL(heateq_bdf2 quick)

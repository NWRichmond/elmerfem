IF(WITH_LUA)
  INCLUDE(test_macros)
  INCLUDE_DIRECTORIES(${CMAKE_BINARY_DIR}/fem/src)

  CONFIGURE_FILE( case.sif case.sif COPYONLY)
  ADD_ELMERTEST_MODULE(KeywordUnitTestLua KeywordCompareTensor KeywordCompareTensor.F90)

  file(COPY ELMERSOLVER_STARTINFO KeywordCompareTensor.F90 square.grd DESTINATION "${CMAKE_CURRENT_BINARY_DIR}/")

  ADD_ELMER_TEST(KeywordUnitTestLua LABELS lua matc quick)
ENDIF(WITH_LUA)

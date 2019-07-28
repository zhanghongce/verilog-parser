FILE(GLOB TEST_VLOG_SRCS *.v)

foreach(VLOG_FILE ${TEST_VLOG_SRCS})

  add_test(
    NAME "test_${VLOG_FILE}"
    COMMAND ${CMAKE_BINARY_DIR}/src/verilogparserexec ${VLOG_FILE}
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
  )

endforeach()

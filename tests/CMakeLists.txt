FILE(GLOB TEST_VLOG_SRCS *.v)

if ("${CMAKE_SYSTEM_NAME}" MATCHES "[Ww]indows")
  set(VLOG_TEST_EXEC "${CMAKE_BINARY_DIR}\src\verilogparserexec.exe")
else()
  set(VLOG_TEST_EXEC "${CMAKE_BINARY_DIR}/src/verilogparserexec")
endif()

foreach(VLOG_FILE ${TEST_VLOG_SRCS})
  add_test(
    NAME "test_${VLOG_FILE}"
    COMMAND ${VLOG_TEST_EXEC} ${VLOG_FILE}
    WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}
  )
endforeach()

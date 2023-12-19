cmake_minimum_required(VERSION 3.0.0)
project(hello_world VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

add_executable(hello_world main.cpp)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
#set(MYVAR "Terapong potisuwan")

include(CPack)

#message("Project name    = ${PROJECT_NAME}")
#message("Project version = ${PROJECT_VERSION}")

function(print)
#ประมาน ว่าต้องใส่ ข้อมูลเข้ามา
#macro(print)
    foreach(var ${ARGN})
        message("${var} = ${${var}}")
    endforeach()
    
    set(MYVAR "no longer say hrllo...")

#    message("${var} = ${${var}}")
#    message("${ARGN}")
#    message("${ARGC}")
#    message("${ARGV0}")
#    message("${ARGV1}")
#    message("${ARGV2}")
#    message("${ARGV3}")
#endmacro()
endfunction()

set(MYVAR "Ying potisuwan")
function(print_env)
    foreach(var ${ARGN})
        message("${var} = ${${var}}")
    endforeach()
    
    set(MYVAR "no longer say hrllo...")
endfunction()

#print(PROJECT_NAME PROJECT_NAME_FOO MYVAR)
print(MYVAR)
print_env(MYVAR)
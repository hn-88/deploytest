cmake_minimum_required(VERSION 2.4.7)
PROJECT(GL_warp2mp4)

set(CMAKE_MODULE_PATH "${PROJECT_SOURCE_DIR}/cmake_modules/")


include_directories( )

aux_source_directory(. SRC_LIST)

foreach(F ${SRC_LIST})
    string(LENGTH ${F} NAMELENGTH)
    string(SUBSTRING ${F} 0 ${NAMELENGTH} FILENAME)
    string(REPLACE .cpp .bin FILENAME1 ${FILENAME})
    add_executable(${FILENAME1} ${F} )
    target_link_libraries(${FILENAME1}  )
endforeach(F)

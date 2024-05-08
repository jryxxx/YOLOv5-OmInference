cmake_minimum_required(VERSION 3.5.1)
project(sampleYOLOV7)
add_compile_options(-std=c++11)
add_definitions(-DENABLE_DVPP_INTERFACE)

set(INC_PATH "/usr/local/Ascend/ascend-toolkit/latest")
set(LIB_PATH "/usr/local/Ascend/ascend-toolkit/lastest/runtime/lib64/stub")
set(THIRDPART "/usr/local/Ascend/thirdpart")

include_directories(
   ${INC_PATH}/runtime/include/
   ${THIRDPART}/aarch64/include/acllite
)

link_directories(
	/usr/local/Ascend/ascend-toolkit/8.0.RC1.alpha003/runtime/lib64/
    ${THIRDPART}/aarch64/lib/
    ${LIB_PATH}
)

add_executable(main sampleYOLOV7.cpp)

target_link_libraries(main ascendcl acl_dvpp stdc++ acllite opencv_core opencv_imgproc opencv_imgcodecs dl rt)



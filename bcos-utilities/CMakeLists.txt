file(GLOB SRC_LIST "*.cpp")
file(GLOB HEADERS "*.h")

SET(Boost_USE_STATIC_LIBS ON)
find_package(Boost REQUIRED COMPONENTS log chrono system thread)

add_library(${BCOS_UTILITIES_TARGET} ${SRC_LIST} ${HEADERS})
target_link_libraries(${BCOS_UTILITIES_TARGET} PUBLIC Boost::log Boost::chrono Boost::thread)
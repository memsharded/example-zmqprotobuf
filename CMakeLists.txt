PROJECT(MyHello)
cmake_minimum_required(VERSION 3.0)

include(conanbuildinfo.cmake)
CONAN_BASIC_SETUP()

ADD_LIBRARY(message message.pb.cc)
ADD_EXECUTABLE(client client.cpp)
ADD_EXECUTABLE(server server.cpp)
TARGET_LINK_LIBRARIES(client message ${CONAN_LIBS})
TARGET_LINK_LIBRARIES(server message ${CONAN_LIBS})
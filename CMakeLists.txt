cmake_minimum_required(VERSION 3.13)

set(PROJECT_NAME cmake_project_example)
set(CMAKE_CXX_STANDARD 17)

project(${PROJECT_NAME})
add_executable(${PROJECT_NAME} src/main.cpp) #실행파일


#컴파일 실행 커맨드 -B{}:빌드할 폴더 지정 경로지정: 빌드 타입
#cmake -Bbuild . DCMAKE_BUILD_TYPE=Debug | Release

#빌드 실행 커맨드 이후 실행파일 생성됨
#cmake --build build

#실행파일 실행 커맨드
#.\build\Debug\cmake_project_example.exe

include(Dependency.cmake)

# 우리 프로젝트에 include / lib 관련 옵션 추가
target_include_directories(${PROJECT_NAME} PUBLIC ${DEP_INCLUDE_DIR})
target_link_directories(${PROJECT_NAME} PUBLIC ${DEP_LIB_DIR})
target_link_libraries(${PROJECT_NAME} PUBLIC ${DEP_LIBS})

# Dependency들이 먼저 build 될 수 있게 관계 설정
add_dependencies(${PROJECT_NAME} ${DEP_LIST})
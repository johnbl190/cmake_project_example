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
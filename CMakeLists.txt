cmake_minimum_required(VERSION 3.16)
project(C++Primer)

set(CMAKE_CXX_STANDARD 11)

#add_executable(LeetCode main.cpp 001TwoSum.cpp)
# 遍历项目根目录下所有的 .cpp 文件
#file (GLOB files *.cpp)
#file (GLOB files *.cpp */*cpp)
file (GLOB files *.cpp */*.cpp */*/*.cpp)
foreach (file ${files})
    string(REGEX REPLACE ".+/(.+)\\..*" "\\1" exe ${file})
    add_executable (${exe} ${file})
    message (\ \ \ \ --\ src/${exe}.cpp\ will\ be\ compiled\ to\ bin/${exe})
endforeach ()
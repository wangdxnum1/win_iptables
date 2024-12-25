# 查找并包含 GTest
find_package(GTest REQUIRED)

# 添加测试可执行文件
add_executable(runTests test_main.cc)

# 链接 GTest 库
target_link_libraries(runTests PRIVATE GTest::GTest GTest::Main)

# 确保 runTests 可以找到 win_iptables 的头文件
target_include_directories(runTests PRIVATE ${CMAKE_SOURCE_DIR}/src)

# 如果需要链接 win_iptables 的库或者静态库，请在这里进行设置

# 添加测试命令
enable_testing()
add_test(NAME runTests COMMAND runTests)
#Copyright (c) Microsoft. All rights reserved.
#Licensed under the MIT license. See LICENSE file in the project root for full license information.

#this is CMakeLists.txt for edge_openssl_common_ut
cmake_minimum_required(VERSION 2.8.11)

compileAsC11()

set(theseTestsName edge_openssl_common_ut)

include_directories(../../src)

add_definitions(-DGB_DEBUG_ALLOC)

set(${theseTestsName}_test_files
    ${theseTestsName}.c
)

set(${theseTestsName}_c_files
    openssl_mocked.c
)

set(${theseTestsName}_h_files
    ../../src/edge_openssl_common.h

)

build_c_test_artifacts(${theseTestsName} ON "tests/azure_c_shared_utility_tests")

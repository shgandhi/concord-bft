add_library(lib_db_editor INTERFACE)
target_link_libraries(lib_db_editor INTERFACE)
target_include_directories(lib_db_editor INTERFACE include)

if(BUILD_ROCKSDB_STORAGE)
add_executable(sparse_merkle_db_editor src/sparse_merkle_db_editor.cpp)
target_link_libraries(sparse_merkle_db_editor PUBLIC lib_db_editor util kvbc stdc++fs)
add_executable(kv_blockchain_db_editor src/kv_blockchain_db_editor.cpp)
target_link_libraries(kv_blockchain_db_editor PUBLIC lib_db_editor util kvbc stdc++fs)
endif()

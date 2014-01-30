#
# Set CMake minimum version
cmake_minimum_required(VERSION 2.8)

#
# Name the project
project(leveldb)

add_definitions(
   # Required for Windows port
   -DLEVELDB_PLATFORM_WINDOWS
   # Required for Windows port
   -DOS_WIN
   # Disable secure CRT warnings
   -D_CRT_SECURE_NO_WARNINGS
   # Disable "signed/unsigned mismatch" warning
   -wd4018
   # Disable "conversion from 'uint64_t' to 'size_t'" warning
   -wd4244
   # Disable "forcing value to bool 'true' or 'false'" warning
   -wd4800
   # Disable "POSIX name for this item is deprecated" warning
   -wd4996
   )

#
# Add include directories
include_directories(
   ${CMAKE_CURRENT_SOURCE_DIR}
   ${CMAKE_CURRENT_SOURCE_DIR}/include
   ${CMAKE_CURRENT_SOURCE_DIR}/port/win
)

#
# Add static library
add_library(
   leveldb
   db/builder.cc
   db/c.cc
   db/dbformat.cc
   db/db_impl.cc
   db/db_iter.cc
   db/filename.cc
   db/log_reader.cc
   db/log_writer.cc
   db/memtable.cc
   db/repair.cc
   db/table_cache.cc
   db/version_edit.cc
   db/version_set.cc
   db/write_batch.cc
   helpers/memenv/memenv.cc
   port/port_win.cc
   table/block.cc
   table/block_builder.cc
   table/filter_block.cc
   table/format.cc
   table/iterator.cc
   table/merger.cc
   table/table.cc
   table/table_builder.cc
   table/two_level_iterator.cc
   util/arena.cc
   util/bloom.cc
   util/cache.cc
   util/coding.cc
   util/comparator.cc
   util/crc32c.cc
   util/env.cc
   util/env_win.cc
   util/filter_policy.cc
   util/hash.cc
   util/logging.cc
   util/options.cc
   util/status.cc
   )

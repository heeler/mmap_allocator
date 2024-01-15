cmake_minimum_required(VERSION 3.19)
project(mmap_allocator VERSION 1.2.1)

set(ma_src_h
        mmap_access_mode.h
        mmap_allocator.h
        mmap_exception.h
        mmap_file_pool.h
        mmappable_vector.h
)

set(ma_src_cpp
        mmap_file_pool.cpp
)

set(MMAP_LIB_TARGET mmapacc)

add_library(${MMAP_LIB_TARGET} STATIC ${ma_src_h} ${ma_src_cpp} )
install(TARGETS ${MMAP_LIB_TARGET} DESTINATION lib/libmmapacc)
install(FILES ${ma_src_h}
        DESTINATION include/libmmapacc)

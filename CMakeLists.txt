project (reiserfs-defrag)

cmake_minimum_required (VERSION 2.6)

add_executable (reiserfs-defrag
	src/defrag.cpp
	src/reiserfs.cpp
	src/journal.cpp
	src/bitmap.cpp
	src/block.cpp
	src/progress.cpp
	src/entry.cpp
)

target_link_libraries(reiserfs-defrag
	rt
)

set(SBINDIR "${CMAKE_INSTALL_PREFIX}/sbin" CACHE PATH "installation path for binaries (sbin)")

install(TARGETS reiserfs-defrag DESTINATION ${SBINDIR})
install(FILES doc/reiserfs-defrag.8 DESTINATION "share/man/man8")

set(minizip_files crypt.h  ioapi.c  ioapi.h  mztools.c  mztools.h  unzip.c  unzip.h  zip.c  zip.h)
if( MSVC )
  set(minizip_files ${minizip_files} iowin32.c  iowin32.h)
endif()

__add_real_target(minizip lib SOURCE ${minizip_files}
							  LIB zlib
							  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}
							  )


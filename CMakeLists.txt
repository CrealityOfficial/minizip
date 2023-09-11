__cc_find(zlib_static)
__assert_target(zlib_static)

set(minizip_files crypt.h  ioapi.c  ioapi.h  
	mztools.c  mztools.h  unzip.c  unzip.h
	zip.c  zip.h
	)
if( MSVC )
  set(minizip_files ${minizip_files} iowin32.c  iowin32.h)
endif()

__add_real_target(minizip_static lib SOURCE ${minizip_files}
							  ILIB zlib_static
							  INTERFACE ${CMAKE_CURRENT_SOURCE_DIR}
							  )
							  							  							   
if(CC_INSTALL_MINIZIP_STATIC)
	__install_directory_specif(${CMAKE_CURRENT_SOURCE_DIR}/ minizip_static)
endif()


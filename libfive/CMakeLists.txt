add_subdirectory(src)
add_subdirectory(test)

if (GUILE_FOUND)
    add_subdirectory(bind)
endif(GUILE_FOUND)

if(UNIX AND NOT(APPLE))
    set(DEST_DIR "${CMAKE_INSTALL_PREFIX}")
    CONFIGURE_FILE("libfive.pc.in" "libfive.pc" @ONLY)
    install(FILES ${CMAKE_BINARY_DIR}/libfive/libfive.pc DESTINATION lib/pkgconfig)
endif(UNIX AND NOT(APPLE))

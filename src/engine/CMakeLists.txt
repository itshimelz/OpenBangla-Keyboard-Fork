add_subdirectory(common)

## Platform depended things
if (OS_LINUX)
    ## Platform is Linux
    corrosion_import_crate(
        MANIFEST_PATH riti/Cargo.toml
        CRATE_TYPES staticlib
        CRATES riti
    )

    find_package(SQLite3 REQUIRED)
    target_link_libraries(riti INTERFACE SQLite3::SQLite3)

    add_subdirectory(fcitx)
endif (OS_LINUX)

if (APPLE)
    ## Platform is macOS
    add_subdirectory(macOS)
endif (APPLE)

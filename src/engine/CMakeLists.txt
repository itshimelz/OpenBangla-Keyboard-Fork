add_subdirectory(common)

## Platform depended things
if (OS_LINUX)
    ## Platform is Linux
    corrosion_import_crate(
        MANIFEST_PATH riti/Cargo.toml
        CRATE_TYPES staticlib
        CRATES riti
    )

    add_subdirectory(fcitx)
endif (OS_LINUX)

if (APPLE)
    ## Platform is macOS
    add_subdirectory(macOS)
endif (APPLE)

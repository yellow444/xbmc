set(SOURCES archive.cpp
            arcread.cpp
            cmddata.cpp
            consio.cpp
            crc.cpp
            crypt.cpp
            encname.cpp
            errhnd.cpp
            extinfo.cpp
            extract.cpp
            filcreat.cpp
            file.cpp
            filefn.cpp
            filestr.cpp
            find.cpp
            getbits.cpp
            global.cpp
            int64.cpp
            isnt.cpp
            log.cpp
            match.cpp
            options.cpp
            pathfn.cpp
            rar.cpp
            rarvm.cpp
            rawread.cpp
            rdwrfn.cpp
            recvol.cpp
            resource.cpp
            rijndael.cpp
            rs.cpp
            savepos.cpp
            scantree.cpp
            sha1.cpp
            strfn.cpp
            strlist.cpp
            system.cpp
            timefn.cpp
            ulinks.cpp
            unicode.cpp
            unpack.cpp
            volume.cpp)

core_add_library(unrarxlib)

if(CORE_SYSTEM_NAME STREQUAL windows)
  target_compile_definitions(unrarxlib PRIVATE -D_XBMC)
  add_precompiled_header(unrarxlib rar.hpp rar.cpp
                         EXCLUDE_SOURCES consio.cpp global.cpp)
else()
  target_compile_definitions(unrarxlib PRIVATE -DSILENT)
endif()

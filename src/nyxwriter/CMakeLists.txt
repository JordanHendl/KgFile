
SET( NYX_FILE_WRITER_SOURCES 
     NyxWriter.cpp
   )
     
SET( NYX_FILE_WRITER_HEADERS
     NyxWriter.h
   )

SET( NYX_FILE_WRITER_INCLUDE_DIRS
     
   )

SET( NYX_FILE_WRITER_LIBRARIES
     glslang
     SPIRV
     stdc++fs
    )

ADD_LIBRARY               ( nyxwriter SHARED   ${NYX_FILE_WRITER_SOURCES}  ${NYX_FILE_WRITER_HEADERS} )
TARGET_INCLUDE_DIRECTORIES( nyxwriter PRIVATE  ${NYX_FILE_WRITER_INCLUDE_DIRS}                        )
TARGET_LINK_LIBRARIES     ( nyxwriter PUBLIC   ${NYX_FILE_WRITER_LIBRARIES}                           )

INSTALL( TARGETS nyxwriter glslang SPIRV OGLCompiler OSDependent HLSL EXPORT NyxFile 
         ARCHIVE  DESTINATION ${EXPORT_LIB_DIR}
         RUNTIME  DESTINATION ${EXPORT_LIB_DIR}
         LIBRARY  DESTINATION ${EXPORT_LIB_DIR} 
       )

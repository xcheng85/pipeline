
#includes

#sources
set(SOURCES
  src/Manipulator.cpp
  src/Renderer.cpp
  src/RendererOptions.cpp
  src/SceneRenderer.cpp
  src/SceniXWidget.cpp
  src/Trackball.cpp
  src/ViewState.cpp
)

set(PRIVATE_HEADERS
)

set(PUBLIC_HEADERS
  Config.h
  HumanInterfaceDevice.h
  Manipulator.h
  Renderer.h
  RendererOptions.h
  SceneRenderer.h
  SceniXWidget.h
  Trackball.h
  ViewState.h
)

source_group(source FILES ${SOURCES})
source_group(header FILES ${PRIVATE_HEADERS})
source_group(""     FILES ${PUBLIC_HEADERS})

#target
add_library( DPSgUI OBJECT
  ${SOURCES}
  ${HEADERS}
  ${PUBLIC_HEADERS}
)

set_target_properties( DPSgUI PROPERTIES COMPILE_DEFINITIONS DP_SG_UI_EXPORTS )

add_subdirectory( manipulator )

add_subdirectory( qt5 )
add_subdirectory(glut)

set_target_properties( DPSgUI PROPERTIES FOLDER "DP/SG/UI" )

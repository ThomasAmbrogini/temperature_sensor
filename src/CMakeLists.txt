add_executable(${CMAKE_PROJECT_NAME})

target_sources(${CMAKE_PROJECT_NAME}
    PRIVATE
        ${CMAKE_SOURCE_DIR}/coco/src/startup/startup_stm32f4.s
    PRIVATE
        main_stm32.cc
)

target_link_libraries(${CMAKE_PROJECT_NAME}
    PRIVATE
        coco
)

target_compile_definitions(${CMAKE_PROJECT_NAME}
    PRIVATE
        STM32F446xx
)

target_compile_options(${CMAKE_PROJECT_NAME}
    PRIVATE
        -fno-rtti
        -fno-exceptions
)

target_link_options(${CMAKE_PROJECT_NAME}
    PRIVATE
        LINKER:-L${CMAKE_SOURCE_DIR}
        LINKER:-L${CMAKE_SOURCE_DIR}/linker
        LINKER:-T${CMAKE_SOURCE_DIR}/linker/stm32f446ze.ld
)


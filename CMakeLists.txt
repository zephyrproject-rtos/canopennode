if(CONFIG_CANOPENNODE)
zephyr_interface_library_named(CANOPENNODE)

target_include_directories(CANOPENNODE INTERFACE stack)

zephyr_include_directories(.)
zephyr_include_directories(stack)

zephyr_library()
zephyr_library_sources(
    CANopen.c
    stack/CO_Emergency.c
    stack/CO_HBconsumer.c
    stack/CO_NMT_Heartbeat.c
    stack/CO_PDO.c
    stack/CO_SDO.c
    stack/CO_SDOmaster.c
    stack/CO_SYNC.c
    stack/CO_TIME.c
    stack/CO_trace.c
)

zephyr_library_link_libraries(CANOPENNODE)
target_link_libraries(CANOPENNODE INTERFACE zephyr_interface)
endif()

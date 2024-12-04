

if(CONFIG_USB_HOST_VEETHREE)

set(ZEPHYR_CURRENT_LIBRARY usb_host_veethree)

zephyr_interface_library_named(USB_HOST_VEETHREE)
zephyr_library()

zephyr_include_directories(usb/include)
zephyr_include_directories(usb/host)
zephyr_include_directories(usb/phy)
zephyr_include_directories(usb/host/class)
zephyr_include_directories(osa)
zephyr_include_directories(lists)



zephyr_library_sources(

usb/host/class/usb_host_hub_app.c
usb/host/class/usb_host_hub.c 
usb/host/class/usb_host_msd_ufi.c
usb/host/class/usb_host_msd.c 
usb/host/usb_host_devices.c 
usb/host/usb_host_ehci.c 
usb/host/usb_host_framework.c 
usb/host/usb_host_hci.c 
usb/phy/usb_phy.c

osa/fsl_os_abstraction_zephyr.c

lists/fsl_component_generic_list.c
)

zephyr_library_link_libraries(USB_HOST_VEETHREE)
target_link_libraries(USB_HOST_VEETHREE INTERFACE zephyr_interface)

endif()
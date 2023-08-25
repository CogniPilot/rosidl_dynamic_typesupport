# SPDX-License-Identifier: Apache-2.0
if (CONFIG_ROSIDL_DYNAMIC_TYPESUPPORT)

zephyr_library_named(rosidl_dynamic_typesupport)

# we need to be able to include generated header files
zephyr_include_directories(
  ../include/
  )

zephyr_library_sources(
  ../src/api/dynamic_data.c
  ../src/api/dynamic_type.c
  ../src/api/serialization_support.c
  ../src/dynamic_message_type_support_struct.c
  ../src/identifier.c
  )


# necessary for module to calll nanopb_generate
add_dependencies(app rosidl_dynamic_typesupport rcutils)
        
endif()

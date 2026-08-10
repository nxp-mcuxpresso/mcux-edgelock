# Copyright 2026 NXP
# SPDX-License-Identifier: BSD-3-Clause

# rt2660a0-ele-container.h - S100 ELE firmware container for RT2660
if (CONFIG_MCUX_COMPONENT_component.edgelock.s100.rt2660a0_ele_container)
    mcux_add_source(SOURCES rt2660a0-ele-container.h)
    # Add define for array container name
    mcux_add_macro(CC "-Dele_fw=ele_fw_rt2660a0_ele_container")
    # Add define for header file name
    mcux_add_macro(CC "-Dele_fw_header=rt2660a0-ele-container.h")
    mcux_add_include(INCLUDES ./)
endif()

# rt2660a0rsa-ele-container.h - S100 ELE firmware container (RSA) for RT2660 
if (CONFIG_MCUX_COMPONENT_component.edgelock.s100.rt2660a0rsa_ele_container)
    mcux_add_source(SOURCES rt2660a0rsa-ele-container.h)
    # Add define for array container name
    mcux_add_macro(CC "-Dele_fw=ele_fw_rt2660a0rsa_ele_container")
    # Add define for header file name
    mcux_add_macro(CC "-Dele_fw_header=rt2660a0rsa-ele-container.h")
    mcux_add_include(INCLUDES ./)
endif()

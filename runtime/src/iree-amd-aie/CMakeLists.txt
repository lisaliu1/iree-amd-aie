# Copyright 2023 The IREE Authors
#
# Licensed under the Apache License v2.0 with LLVM Exceptions.
# See https://llvm.org/LICENSE.txt for license information.
# SPDX-License-Identifier: Apache-2.0 WITH LLVM-exception

if(IREE_AMD_AIE_ENABLE_XRT_DRIVER)
    add_subdirectory(driver/xrt)
endif()

add_subdirectory(tools)

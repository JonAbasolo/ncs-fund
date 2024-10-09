#
# Copyright (c) 2020 Nordic Semiconductor
#
# SPDX-License-Identifier: LicenseRef-Nordic-5-Clause
#

cmake_minimum_required(VERSION 3.20.0)
find_package(Zephyr REQUIRED HINTS $ENV{ZEPHYR_BASE})

project(nrf_connect_sdk_fundamentals)

target_sources(app PRIVATE src/main.c)

# Honegaz guk definitutako fixategia eta bertan definitutako funtzioak esleitu daikeguz

# target_sources(app PRIVATE src/myfunction.c)    

#Proiektu baten, fitxategi batzuk bakarik erabiliko badira, CONFIG_MYFUNCTION atalean gaitu edo 
#ezgaitu daitekez, eta honela behar ez den kodea kargatzeaz aurresten gara
target_sources_ifdef(CONFIG_MYFUNCTION app PRIVATE src/myfunction.c)


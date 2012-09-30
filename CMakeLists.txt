# Copyright (C) 2007-2012 LuaDist.
# Created by Peter Kapec
# Redistribution and use of this file is allowed according to the terms of the MIT license.
# For details see the COPYRIGHT file distributed with LuaDist.
# Please note that the package source code is licensed under its own license.

project ( luasql C )
cmake_minimum_required ( VERSION 2.8 )
include ( cmake/dist.cmake )
include ( lua )

find_package ( PostgreSQL REQUIRED )
include_directories ( ${POSTGRESQL_INCLUDE_DIR} src )
install_lua_module ( luasql.postgres src/ls_postgres.c src/luasql.c LINK ${POSTGRESQL_LIBRARIES} )

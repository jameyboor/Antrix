# MaNGOS is a full featured server for World of Warcraft, supporting
# the following clients: 1.12.x, 2.4.3, 3.3.5a, 4.3.4a and 5.4.8
#
# Copyright (C) 2005-2015  MaNGOS project <http://getmangos.eu>
#
# This program is free software; you can redistribute it and/or modify
# it under the terms of the GNU General Public License as published by
# the Free Software Foundation; either version 2 of the License, or
# (at your option) any later version.
#
# This program is distributed in the hope that it will be useful,
# but WITHOUT ANY WARRANTY; without even the implied warranty of
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
# GNU General Public License for more details.
#
# You should have received a copy of the GNU General Public License
# along with this program; if not, write to the Free Software
# Foundation, Inc., 59 Temple Place, Suite 330, Boston, MA  02111-1307  USA

# Needs to link against mangos_world.lib
if(WIN32)
  link_directories("${CMAKE_BINARY_DIR}/src/antrix/${CMAKE_CFG_INTDIR}")
endif()

# Build the world server
add_subdirectory(antrix)

# Build the mangos game library
add_subdirectory(game)

# Build the logonserver server
add_subdirectory(logonserver)

# Build the scripts
#add_subdirectory(scripts)

# Build the mangos shared library
add_subdirectory(shared)

# If we want the tools for map extraction
if(BUILD_TOOLS)
    add_subdirectory(tools)
endif()
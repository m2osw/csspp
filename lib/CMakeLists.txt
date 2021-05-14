#
# Copyright (c) 2015-2021  Made to Order Software Corp.  All Rights Reserved
#
# https://snapwebsites.org/
# contact@m2osw.com
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
# Foundation, Inc., 51 Franklin St, Fifth Floor, Boston, MA 02110-1301 USA
#

project(csspp)


add_library( ${PROJECT_NAME} SHARED
    assembler.cpp                               # Write the nodes back out
    csspp.cpp                                   # Some basics about the library
    color.cpp                                   # Manager RGBA colors
    compiler.cpp                                # Work on a tree of node to make it CSS compatible
    error.cpp                                   # Print out error messages
    expression.cpp                              # Reduce expressions, public functions
    expr_additive.cpp                           # Reduce additivice expressions
    expr_conditional.cpp                        # Reduce conditional expressions
    expr_equality.cpp                           # Reduce equality expressions
    expr_list.cpp                               # Reduce list expressions
    expr_logical_and.cpp                        # Reduce logical and expressions
    expr_logical_or.cpp                         # Reduce logical or expressions
    expr_multiplicative.cpp                     # Reduce multiplicative expressions
    expr_power.cpp                              # Reduce power expressions
    expr_relational.cpp                         # Reduce relational expressions
    expr_unary.cpp                              # Reduce unary expressions
    internal_functions.cpp                      # Expression internal function handling
    lexer.cpp                                   # Transform input in tokens
    node.cpp                                    # Holds the data read
    nth_child.cpp                               # Manage An+B
    parser.cpp                                  # Transform tokens in a tree of nodes
    position.cpp                                # Holds the current position
    unicode_range.cpp                           # Handle a Unicode Range value
)

set_target_properties( ${PROJECT_NAME} PROPERTIES
    VERSION ${CSSPP_VERSION_MAJOR}.${CSSPP_VERSION_MINOR}
    SOVERSION ${CSSPP_VERSION_MAJOR}
)

install(
    TARGETS ${PROJECT_NAME}
    RUNTIME DESTINATION bin
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
)


# Local Variables:
# indent-tabs-mode: nil
# tab-width: 4
# End:

# vim: ts=4 sw=4 et nocindent

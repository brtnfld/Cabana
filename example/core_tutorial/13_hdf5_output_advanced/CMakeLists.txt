############################################################################
# Copyright (c) 2018-2022 by the Cabana authors                            #
# All rights reserved.                                                     #
#                                                                          #
# This file is part of the Cabana library. Cabana is distributed under a   #
# BSD 3-clause license. For the licensing terms see the LICENSE file in    #
# the top-level directory.                                                 #
#                                                                          #
# SPDX-License-Identifier: BSD-3-Clause                                    #
############################################################################

add_executable(AdvancedHDF5Output advanced_hdf5_output_example.cpp)
target_link_libraries(AdvancedHDF5Output cabanacore)
add_test(NAME Core_tutorial_13_subfiling COMMAND ${MPIEXEC} ${MPIEXEC_NUMPROC_FLAG}
  ${MPIEXEC_MAX_NUMPROCS} ${MPIEXEC_PREFLAGS} $<TARGET_FILE:AdvancedHDF5Output> ${MPIEXEC_POSTFLAGS})
set_tests_properties(Core_tutorial_13_subfiling PROPERTIES PROCESSORS ${MPIEXEC_MAX_NUMPROCS})

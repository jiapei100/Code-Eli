################################################################################
# Copyright (c) 2013 David D. Marshall <ddmarsha@calpoly.edu>
#
# All rights reserved. This program and the accompanying materials
# are made available under the terms of the Eclipse Public License v1.0
# which accompanies this distribution, and is available at
# http://www.eclipse.org/legal/epl-v10.html
#
# Contributors:
#    David D. Marshall - initial code and implementation
################################################################################

project(PIECEWISE_CURVE_TESTS)

# add the piecewise_curve test
set (PIECEWISE_CURVE_TEST_EXE PiecewiseCurveTest)
set (PIECEWISE_CURVE_TEST_SOURCE ${PROJECT_SOURCE_DIR}/piecewise_curve_test.cpp)
set (PIECEWISE_CURVE_TEST_HEADER ${PROJECT_SOURCE_DIR}/piecewise_curve_test_suite.hpp
                                 ${ELI_SOURCE_DIR}/include/eli/constants/math.hpp
                                 ${ELI_SOURCE_DIR}/include/eli/util/tolerance.hpp
                                 ${ELI_SOURCE_DIR}/include/eli/mutil/fd/d1o2.hpp
                                 ${ELI_SOURCE_DIR}/include/eli/geom/general/continuity.hpp
                                 ${ELI_SOURCE_DIR}/include/eli/geom/curve/bezier.hpp
                                 ${ELI_SOURCE_DIR}/include/eli/geom/curve/length.hpp
                                 ${ELI_SOURCE_DIR}/include/eli/geom/curve/curvature.hpp
                                 ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise.hpp
                                 ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_creator_base.hpp)

add_executable(${PIECEWISE_CURVE_TEST_EXE} ${PIECEWISE_CURVE_TEST_SOURCE} ${PIECEWISE_CURVE_TEST_HEADER})
target_link_libraries(${PIECEWISE_CURVE_TEST_EXE} ${_ELI_TEST_LIBRARIES_LIST})
add_test(NAME ${PIECEWISE_CURVE_TEST_EXE} COMMAND $<TARGET_FILE:${PIECEWISE_CURVE_TEST_EXE}> --text)

# add the piecewise_curve_creator test
set (PIECEWISE_CURVE_CREATOR_TEST_EXE PiecewiseCurveCreatorTest)
set (PIECEWISE_CURVE_CREATOR_TEST_SOURCE ${PROJECT_SOURCE_DIR}/piecewise_curve_creator_test.cpp)
set (PIECEWISE_CURVE_CREATOR_TEST_HEADER ${PROJECT_SOURCE_DIR}/piecewise_point_creator_test_suite.hpp
                                         ${PROJECT_SOURCE_DIR}/piecewise_polygon_creator_test_suite.hpp
                                         ${PROJECT_SOURCE_DIR}/piecewise_circle_creator_test_suite.hpp
                                         ${PROJECT_SOURCE_DIR}/piecewise_cubic_spline_creator_test_suite.hpp
                                         ${PROJECT_SOURCE_DIR}/piecewise_superellipse_creator_test_suite.hpp
                                         ${PROJECT_SOURCE_DIR}/piecewise_general_creator_test_suite.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/constants/math.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/util/tolerance.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/mutil/fd/d1o2.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/general/continuity.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/bezier.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/length.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/curvature.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_creator_base.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_point_creator.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_linear_creator.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_polygon_creator.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_circle_creator.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_cubic_spline_creator.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_superellipse_creator.hpp
                                         ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_general_creator.hpp)


add_executable(${PIECEWISE_CURVE_CREATOR_TEST_EXE} ${PIECEWISE_CURVE_CREATOR_TEST_SOURCE} ${PIECEWISE_CURVE_CREATOR_TEST_HEADER})
target_link_libraries(${PIECEWISE_CURVE_CREATOR_TEST_EXE} ${_ELI_TEST_LIBRARIES_LIST})
add_test(NAME ${PIECEWISE_CURVE_CREATOR_TEST_EXE} COMMAND $<TARGET_FILE:${PIECEWISE_CURVE_CREATOR_TEST_EXE}> --text)

# add the piecewise_airfoil_creator test
set (PIECEWISE_AIRFOIL_CREATOR_TEST_EXE PiecewiseAirfoilCreatorTest)
set (PIECEWISE_AIRFOIL_CREATOR_TEST_SOURCE ${PROJECT_SOURCE_DIR}/piecewise_airfoil_creator_test.cpp)
set (PIECEWISE_AIRFOIL_CREATOR_TEST_HEADER ${PROJECT_SOURCE_DIR}/piecewise_four_digit_creator_test_suite.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/constants/math.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/util/tolerance.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/mutil/fd/d1o2.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/mutil/fd/d2o2.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/geom/general/continuity.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/geom/curve/bezier.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/geom/curve/length.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/geom/curve/curvature.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_creator_base.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/geom/curve/piecewise_four_digit_creator.hpp
                                           ${ELI_SOURCE_DIR}/include/eli/geom/curve/pseudo/four_digit.hpp)


add_executable(${PIECEWISE_AIRFOIL_CREATOR_TEST_EXE} ${PIECEWISE_AIRFOIL_CREATOR_TEST_SOURCE} ${PIECEWISE_AIRFOIL_CREATOR_TEST_HEADER})
target_link_libraries(${PIECEWISE_AIRFOIL_CREATOR_TEST_EXE} ${_ELI_TEST_LIBRARIES_LIST})
add_test(NAME ${PIECEWISE_AIRFOIL_CREATOR_TEST_EXE} COMMAND $<TARGET_FILE:${PIECEWISE_AIRFOIL_CREATOR_TEST_EXE}> --text)

cmake_minimum_required(VERSION 2.8.3)
project(cob_helper_tools)

find_package(catkin REQUIRED COMPONENTS dynamic_reconfigure message_generation)

generate_dynamic_reconfigure_options(
  cfg/HelperTools.cfg
)

catkin_package()

#############
## Install ##
#############

catkin_install_python(PROGRAMS
  scripts/auto_init.py
  scripts/auto_recover.py
  scripts/fake_diagnostics.py
  scripts/fake_driver.py
  scripts/visualize_navigation_goals.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

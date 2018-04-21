# Script generated with Bloom
pkgdesc="ROS - Calibrate a Robot"
url='http://ros.org/wiki/robot_calibration'

pkgname='ros-kinetic-robot-calibration'
pkgver='0.5.5_1'
pkgrel=1
arch=('any')
license=('Apache2'
)

makedepends=('ceres-solver'
'gflags'
'protobuf'
'ros-kinetic-actionlib'
'ros-kinetic-camera-calibration-parsers'
'ros-kinetic-catkin'
'ros-kinetic-control-msgs'
'ros-kinetic-cv-bridge'
'ros-kinetic-geometry-msgs'
'ros-kinetic-kdl-parser'
'ros-kinetic-moveit-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-orocos-kdl'
'ros-kinetic-robot-calibration-msgs'
'ros-kinetic-rosbag'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-tf'
'ros-kinetic-tf2-geometry-msgs'
'ros-kinetic-tf2-ros'
'suitesparse'
)

depends=('ceres-solver'
'protobuf'
'ros-kinetic-actionlib'
'ros-kinetic-camera-calibration-parsers'
'ros-kinetic-control-msgs'
'ros-kinetic-cv-bridge'
'ros-kinetic-geometry-msgs'
'ros-kinetic-kdl-parser'
'ros-kinetic-moveit-msgs'
'ros-kinetic-nav-msgs'
'ros-kinetic-orocos-kdl'
'ros-kinetic-robot-calibration-msgs'
'ros-kinetic-rosbag'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
'ros-kinetic-std-msgs'
'ros-kinetic-tf'
'ros-kinetic-tf2-geometry-msgs'
'ros-kinetic-tf2-ros'
'suitesparse'
)

conflicts=()
replaces=()

_dir=robot_calibration
source=()
md5sums=()

prepare() {
    cp -R $startdir/robot_calibration $srcdir/robot_calibration
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}


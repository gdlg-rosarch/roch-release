# Script generated with Bloom
pkgdesc="ROS - SawYer roch controller configurations"
url='http://ros.org/wiki/roch_teleop'

pkgname='ros-kinetic-roch-teleop'
pkgver='2.0.12_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-geometry-msgs'
'ros-kinetic-joy'
'ros-kinetic-roscpp'
'ros-kinetic-roslaunch'
)

depends=('ros-kinetic-controller-manager'
'ros-kinetic-diff-drive-controller'
'ros-kinetic-geometry-msgs'
'ros-kinetic-interactive-marker-twist-server'
'ros-kinetic-joint-state-controller'
'ros-kinetic-joint-trajectory-controller'
'ros-kinetic-joy'
'ros-kinetic-robot-localization'
'ros-kinetic-roscpp'
'ros-kinetic-rostopic'
'ros-kinetic-teleop-twist-joy'
'ros-kinetic-twist-mux'
'ros-kinetic-yocs-cmd-vel-mux'
)

conflicts=()
replaces=()

_dir=roch_teleop
source=()
md5sums=()

prepare() {
    cp -R $startdir/roch_teleop $srcdir/roch_teleop
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


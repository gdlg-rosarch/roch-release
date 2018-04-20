# Script generated with Bloom
pkgdesc="ROS - The roch_rapps package for set of 'app manager' apps definition"
url='http://ros.org/wiki/roch_rapps'

pkgname='ros-kinetic-roch-rapps'
pkgver='2.0.12_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
)

depends=('ros-kinetic-compressed-image-transport'
'ros-kinetic-nodelet'
'ros-kinetic-robot-pose-publisher'
'ros-kinetic-roch-bringup'
'ros-kinetic-roch-follower'
'ros-kinetic-roch-navigation'
'ros-kinetic-roch-teleop'
'ros-kinetic-tf'
'ros-kinetic-topic-tools'
'ros-kinetic-warehouse-ros'
'ros-kinetic-world-canvas-server'
)

conflicts=()
replaces=()

_dir=roch_rapps
source=()
md5sums=()

prepare() {
    cp -R $startdir/roch_rapps $srcdir/roch_rapps
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


# Script generated with Bloom
pkgdesc="ROS - Follower for the roch. Follows humans and robots around by following the centroid of a box points in front of the roch."
url='http://ros.org/wiki/roch_follower'

pkgname='ros-kinetic-roch-follower'
pkgver='2.0.12_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-kinetic-catkin'
'ros-kinetic-depth-image-proc'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-nodelet'
'ros-kinetic-roch-msgs'
'ros-kinetic-roscpp'
'ros-kinetic-visualization-msgs'
)

depends=('ros-kinetic-depth-image-proc'
'ros-kinetic-dynamic-reconfigure'
'ros-kinetic-nodelet'
'ros-kinetic-roch-bringup'
'ros-kinetic-roch-msgs'
'ros-kinetic-roch-teleop'
'ros-kinetic-roscpp'
'ros-kinetic-topic-tools'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=roch_follower
source=()
md5sums=()

prepare() {
    cp -R $startdir/roch_follower $srcdir/roch_follower
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


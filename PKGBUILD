# Script generated with Bloom
pkgdesc="ROS - A ROS camera driver that uses gstreamer to connect to devices such as webcams."


pkgname='ros-kinetic-gscam'
pkgver='0.2.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('gstreamer0.10'
'gstreamer0.10-base-plugins'
'ros-kinetic-camera-calibration-parsers'
'ros-kinetic-camera-info-manager'
'ros-kinetic-catkin'
'ros-kinetic-cv-bridge'
'ros-kinetic-image-transport'
'ros-kinetic-nodelet'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
)

depends=('ros-kinetic-camera-calibration-parsers'
'ros-kinetic-camera-info-manager'
'ros-kinetic-cv-bridge'
'ros-kinetic-image-transport'
'ros-kinetic-nodelet'
'ros-kinetic-roscpp'
'ros-kinetic-sensor-msgs'
)

conflicts=()
replaces=()

_dir=gscam
source=()
md5sums=()

prepare() {
    cp -R $startdir/gscam $srcdir/gscam
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


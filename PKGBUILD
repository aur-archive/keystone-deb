# Maintainer: James Bulmer <nekinie@gmail.com>

pkgname="keystone-deb"
pkgver=2014.1
pkgrel=2
pkgdesc="Openstack identity"
arch=("i686" "x86_64")
url="http://docs.openstack.org/developer/keystone/"
license=("Apache")
groups=("openstack-deb")

depends=(
  "python2"
  "python2-pbr"
  "python2-pam"
  "python2-webob"
  "python2-eventlet"
  "python2-greenlet"
  "python2-netaddr"
  "python2-paste-deploy"
  "python2-paste"
  "python2-routes"
  "python2-six"
  "python2-sqlalchemy"
  "python2-openstack-migrate"
  "python2-passlib"
  "python2-lxml"
  "python2-iso8601"
  "python2-keystoneclient"
  "python2-oslo-config"
  "python2-oslo-messaging"
  "python2-babel"
  "python2-oauthlib"
  "python2-dogpile-cache"
  "python2-jsonschema"
  "python2-pycadf"
  # optional?
  "python2-kombu"
  "python2-amqp"
)

makedepends=("python2-setuptools")

conflicts=(
  "keystone",
  "openstack-keystone-git"
)

source=("http://archive.ubuntu.com/ubuntu/pool/main/k/keystone/keystone_${pkgver}.orig.tar.gz")
md5sums=("f8179fdbf64c9e50d66a3729b5cf8502")

build() {
  cd "${srcdir}/keystone-${pkgver}/"
  python2 setup.py build
}

package() {
  cd "${srcdir}/keystone-${pkgver}/"
  python2 setup.py install --root="${pkgdir}/" --optimize=1
  mkdir "${pkgdir}/etc/"
  cp -a "etc" "${pkgdir}/etc/keystone"
}
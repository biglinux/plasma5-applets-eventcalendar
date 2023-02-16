# Submitter: XavierCLL <xavier.corredor.llano (a) gmail.com>
# Maintainer: Zren <zrenfire@gmail.com>
# Maintainer: Barnabé di Kartola <barnabedikartola@gmail.com>

pkgname=plasma5-applets-eventcalendar
pkgver=76
pkgrel=2
pkgdesc="An extended calendar plasmoid with daily weather forecasts and events from Google Calendar. Also includes a timer and 24 hour forecast graph."
arch=('any')
url="https://github.com/kanocz/plasma-applet-eventcalendar"
license=('GPL')
depends=('plasma-workspace' 'qt5-graphicaleffects' 'python-gobject' 'libcanberra')
makedepends=('bash' 'gettext' 'go')
source=("git+${url}.git")
md5sums=('SKIP')

package() {
    cd plasma-applet-eventcalendar
    ./install
    
    cd package
    mkdir -p $pkgdir/usr/share/plasma/plasmoids/org.kde.plasma.eventcalendar
    cp -r * $pkgdir/usr/share/plasma/plasmoids/org.kde.plasma.eventcalendar

    cd $pkgdir/usr/share/plasma/plasmoids/org.kde.plasma.eventcalendar/translate
    sh ./build
    mkdir -p $pkgdir/usr/share/locale
    mv $pkgdir/usr/share/plasma/plasmoids/org.kde.plasma.eventcalendar/contents/locale $pkgdir/usr/share/
    rm -rf $pkgdir/usr/share/plasma/plasmoids/org.kde.plasma.eventcalendar/translate
}


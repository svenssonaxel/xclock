xclock is the classic X Window System clock utility.  It displays
the time in analog or digital form, continuously updated at a
frequency which may be specified by the user.

**This fork adds the following functionality:**
* `-analog24` option to use a 24 hour analog clock face.
* `-circular` option to always draw a circular clock face.

All questions regarding this software should be directed at the
Xorg mailing list:

  https://lists.x.org/mailman/listinfo/xorg

The primary development code repository can be found at:

  https://gitlab.freedesktop.org/xorg/app/xclock

Please submit bug reports and requests to merge patches there.

For patch submission instructions, see:

  https://www.x.org/wiki/Development/Documentation/SubmittingPatches

# Building and installing

## Debian and Ubuntu

```sh
# Get dependencies
sudo apt-get update -y
sudo apt-get install -y autoconf gcc gettext libxaw7-dev libxft-dev libxkbfile-dev make pkg-config xutils-dev
# Build
./autogen.sh
make
# Install
sudo make install
```

# Configuration example

Put the following in `~/.Xresources`:
```
! General xclock settings
XClock.Clock.analog24: true
XClock.Clock.update: 1
XClock.Clock.background: #191919
XClock.Clock.height: 164
XClock.Clock.width: 164

! Settings for xclock -norender
XClock.Clock.hands: #5060cc
XClock.Clock.highlight: #7080ff
XClock.Clock.foreground: #90a0ff
XClock.Clock.padding: 20

! Settings for xclock -render
XClock.Clock.hourColor: #304099
XClock.Clock.minuteColor: #5060cc
XClock.Clock.secondColor: #7080ff
XClock.Clock.majorColor: #cc6050
XClock.Clock.minorColor: #5060cc
XClock.Clock.circular: true
```

Load the X resources and start xclock:
```sh
xrdb ~/.Xresources
xclock
```

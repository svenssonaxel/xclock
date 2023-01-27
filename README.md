xclock is the classic X Window System clock utility.  It displays
the time in analog or digital form, continuously updated at a
frequency which may be specified by the user.

This fork also has the capability to display a 24 hour analog clock.

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
XClock.Clock.analog24: true
XClock.Clock.update: 1
XClock.Clock.hourColor: #102077
XClock.Clock.minuteColor: #3040bb
XClock.Clock.secondColor: #5060ff
XClock.Clock.majorColor: #772010
XClock.Clock.minorColor: #102077
XClock.Clock.background: #191919
```

Load the X resources and start xclock:
```sh
xrdb ~/.Xresources
xclock
```

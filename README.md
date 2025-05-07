xclock is the classic X Window System clock utility.  It displays
the time in analog or digital form, continuously updated at a
frequency which may be specified by the user.

**This fork adds the following functionality:**
* `-analog24` option to use a 24 hour analog clock face.
* `-circular` option to always draw a circular clock face.
* AM/PM marker
* Configurable shapes for hands, tick marks and AM/PM marker.

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
XClock.Clock.amColor: #772010
XClock.Clock.pmColor: #304099
XClock.Clock.hourShape: (-5, 30) (0, 5) (0, 40) -2 -2 (5, 30)
XClock.Clock.minuteShape: (-5, 60) (0, 10) (0, 70) -2 -2 (5, 60)
XClock.Clock.secondShape: (-3, 15) (0, 17) (0, 19) -2 -2 (3, 15) \
                          (-3, 17) (0, 19) (0, 21) -2 -2 (3, 17) \
                          (-3, 19) (0, 21) (0, 23) -2 -2 (3, 19) \
                          (-3, 86) (0, 88) (0, 89) -2 -2 (3, 86) \
                          (-1, 21) (1, 21) (0, 90)
XClock.Clock.majorShape: (2, 99) (-2, 99) (0, 94) (0, 94) (2, 99) (3, 96) (0, 94) (-2, 99) (-3, 96)
XClock.Clock.minorShape: (2, 99) (-2, 99) (0, 95)
XClock.Clock.amShape: (41, -5) (43, -5) (43, 5) -2 -2 (45, 5) \
                      -1 (47, 5) (47, -5) -2 -2 (49, -5) \
                      (43, -1) (43, -3) (47, -1) -2 -2 (47, -3) \
                      (50, -5) (52, -5) (50, 5) -2 -2 (52, 5) \
                      -2 -2 (53, -5) -2 -2 (55, -5) \
                      -2 -2 (56, 5) -2 -2 (58, 5) \
                      -2 -2 (56, -5) -2 -2 (58, -5)
XClock.Clock.pmShape: (43, -5) (45, -5) (43, 5) -2 -2 (45, 5) \
                      -1 (45, 3) (49, 5) -2 -2 (49, 3) \
                      -1 (47, 3) (49, -1) -2 -2 (47, -1) \
                      -1 (47, 1) (45, -1) -2 -2 (45, 1) \
                      (50, -5) (52, -5) (50, 5) -2 -2 (52, 5) \
                      -2 -2 (53, -5) -2 -2 (55, -5) \
                      -2 -2 (56, 5) -2 -2 (58, 5) \
                      -2 -2 (56, -5) -2 -2 (58, -5)
XClock.Clock.circular: true
```

Load the X resources and start xclock:
```sh
xrdb ~/.Xresources
xclock
```

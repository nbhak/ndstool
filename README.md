# ndstool
This is the fork of [ndstool](https://github.com/devkitPro/ndstool)
I used to build the executable for macOS. I intend to put compiled binaries
for all platforms in the ROM-editing tool I'm developing, but I've published
to this repo for reference.

## Prerequisites
Basic build tools:
```
xcode-select --install
```
Homebrew:
```
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
GNU Autotools:
```
brew install autoconf automake libtool
```
## Build
Enter the `ndstool` directory:
```
cd external/ndstool
```
On macOS, there may be an m4 issue due to a version conflict between Xcode's
m4 and what autoconf expects. You can fix this by using the GNU autotools
from Homebrew instead:
```
export PATH="/opt/homebrew/opt/m4/bin:$PATH"
```
Complete remaining build steps:
```
autoreconf -fi
./configure
make
```
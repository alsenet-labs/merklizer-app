# merklizer-app
Mobile app for Merklizer

## Copyright
 Copyright (c) 2018 ALSENET SA

## Authors
  * Alexandre Poltorak <polto@alsenet.com>
  * Luc Deschenaux <luc.deschenaux@freesurf.ch>

## Licence
 This program is free software: you can redistribute it and/or modify
 it under the terms of the GNU Affero General Public License as published by
 the Free Software Foundation, either version 3 of the License, or
 (at your option) any later version.

 This program is distributed in the hope that it will be useful,
 but WITHOUT ANY WARRANTY; without even the implied warranty of
 MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
 GNU Affero General Public License for more details.

 You should have received a copy of the GNU Affero General Public License
 along with this program.  If not, see <http://www.gnu.org/licenses/>.

## Build and test

```
git clone --recursive https://github.com/alsenet-labs/merklizer-app
cd merklizer-app/merklizer
yarn
gulp build
gulp dist
cd ../app
yarn
cordova platform add android
gulp build
gulp run
```

## Troubleshooting

### EACCESS error when building project
Message:
```
(...)/platforms/android/cordova/node_modules/q/q.js:570:49 code: 'EACCES', errno: 'EACCES', syscall: 'spawn' }
```
Fix with:
```
sudo chmod 755 $(which gradle)
```

### INSTALL_FAILED_UPDATE_INCOMPATIBLE when running project
Uninstall the conflicting version - directly from the phone, or with adb:
```
adb uninstall com.alsenet.merklizer
```

### Chrome remote device inspector window is blank (cannot use debugger)
You need to upgrade up to the latest Android SDK and to the latest stable Chrome/Chromium version.
For the latter maybe you need to upgrade to the latest version of your operating system.


# pkgbase(8)

FreeBSD `pkgbase(8)` upgrade tool in PKGBASE world similar to `freebsd-update(8)` command.

## Usage

```
freebsd # pkgbase
usage:
  pkgbase upgrade -r VERSION [-L] [-B]
  pkgbase loader
  pkgbase pkgnew
  pkgbase modules
  pkgbase version
  pkgbase help

options:
  -r VERSION  FreeBSD version you want to upgrade to
  -L          omit UEFI/BIOS bootcode upgrade process
  -B          omit ZFS Boot Environment creation
```

## Example

```
freebsd # pkgbase upgrade -r 15.2-BETA2
INFO: upgrading from '15.2-BETA1' to '15.2-BETA2' version
Updating FreeBSD-ports repository catalogue...
(...)
```

## Changelog

**0.5**
- Add `-B` option to omit ZFS Boot Environment creation and move that into `__zfsbe()` function.
- Remove `RET_VAL` variables.
- Use `getopts(1)` for arguments parsing.

**0.4**
- Add support for *-RELEASE to *-RELEASE upgrade.
- Add additional argument verification.

**0.3**
- Take care of all ZFS pool disks to update bootcode.
- Automatically Create ZFS Boot Environment on ZFS systems.
- Add version information.
- Add option to NOT update BIOS/UEFI bootcode.
- Rename `pkgbase-update(8)` into `pkgbase(8)` for simplicity.
- Add additional check if first `pkg(8)` update works.
- More information messages.
- Better checks.
- Add check for PKGBASE FreeBSD system.
  
**0.2**
- Add UFS support.
- Add PRERELEASE target support.
- Add BIOS bootcode update.
- Add comments.

**0.1**
- Initial working version.






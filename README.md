# rinetd-ng

An experimental, community-maintained fork of [rinetd](https://github.com/samhocevar/rinetd) by Thomas Boutell and Sam Hocevar.

**Status: 1.0 RC2 engineering — NOT production-certified.**

The upstream history and copyright are preserved. Source license: **GNU GPL-2.0-or-later**. This independent fork is not endorsed by the upstream authors.

## Scope

- TCP and UDP port redirection on Linux
- Existing `rinetd.conf` syntax (TCP is implicit; writing `/tcp` or `/udp` explicitly is recommended)
- Experimental signal-safe reload fixes, validated on Rocky Linux 10 laboratory systems
- Proposed support: Rocky Linux 8/9/10 and Ubuntu Server 22.04/24.04/26.04 LTS

## Release status and caution

The experimental RC2 bundle has been tested locally by the project maintainer, including 1,000 concurrent TCP echo sessions on Rocky Linux 10. **This Git branch is a staging branch**: the tested RC2 scripts and test suite have not yet been committed in full; do not treat this branch as the installable RC2 release.

**Blocking work before 1.0:** transactional reload with rollback; long-lived TCP session preservation; sanitizers and multi-distribution RPM/DEB qualification.

## Repository layout and next steps

The original C source and its history remain intact in `main`. Experimental changes should be developed and reviewed on `develop`.

To bring the tested RC2 engineering bundle into this branch while keeping upstream history, see [docs/IMPORT-RC2.md](docs/IMPORT-RC2.md). Do not commit credentials, lab logs, `.venv/`, generated binaries, or build caches.

## Credits

Copyright notices in upstream files remain with their respective holders. Original project: Thomas Boutell and Sam Hocevar. Modifications should be credited separately under the same compatible GPL licensing terms.

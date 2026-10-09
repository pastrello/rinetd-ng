# rinetd-ng — Linux unified development bundle

A GPL-2.0-or-later derivative of **rinetd** by Thomas Boutell and Sam Hocevar.

## One entrypoint

On **Rocky Linux 8/9/10** and **Ubuntu Server 22.04/24.04/26.04 LTS**:

```bash
sudo ./install.sh
```

No separate patch bundles are needed. The install script detects the distribution,
installs build prerequisites, imports the original upstream **pinned commit** if
`upstream/` is absent, applies the development changes, builds and runs acceptance
checks (requires `pytest`), and installs without starting the service.

**Important limitation:** this ZIP does *not* contain the original upstream source.
A GitHub connection is required on first install; existing pinned upstream trees
can be reused offline. It is not a fully self-contained/offline source archive.

For test/build separately: `./install.sh --build-only` or `./install.sh --test-only`.
The script will not overwrite existing `/etc/rinetd.conf` and does not start or
restart rinetd. **Do not run it on production servers without reviewing the
upstream pin, source changes, service security and test requirements.**

## Development status

This is a **development/RC1 candidate bundle**, not a final or transactional
reload implementation. The 100ms select timeout is a provisional fix validated
in an earlier Rocky 10 lab. Rollback, live TCP preservation and OS-package
builds remain unverified. RPM/DEB recipes are preliminary and not certified.

## Source and license

The upstream Git repository at https://github.com/samhocevar/rinetd is pinned
to `d4e0a60119a575b851d6b5e6268491f432d91089`. Its copyright notices and
`COPYING` are preserved in `upstream/` after import.

## Guia de parâmetros do rinetd.conf

Consulte **[docs/CONFIGURATION.md](docs/CONFIGURATION.md)** para a sintaxe completa de encaminhamento, TCP/UDP, `allow`/`deny`, `timeout`, `src`, logs, PID, exemplos de SSH e observações importantes sobre reload.

## Stress test
Run `./install.sh --test-stress` after building. See [docs/STRESS.md](docs/STRESS.md). No stress test is run during installation.


## RC2 engineering additions

See [RC2 status](docs/RC2-STATUS.md). Commands: `./install.sh --test-resilience`, `./install.sh --check-release`, `./tools/build-sanitized.sh`, `./tools/build-deb.sh`. Release gate intentionally fails while the transactional reload is missing.

# Release qualification status

| Gate | Status |
|---|---|
| TCP/UDP basic echo on Rocky Linux 10 | Passed in lab |
| UDP SIGHUP regression and real destination switch | Passed in lab |
| 1,000 concurrent TCP echo sessions (Rocky 10) | Passed in lab |
| Transactional reload with rollback | **Not implemented** |
| Preservation of TCP sessions during reload | Not established |
| ASan/UBSan full runtime acceptance | Not established |
| RPM packages on Rocky 8, 9 and 10 | Not established |
| DEB packages on Ubuntu 22.04, 24.04 and 26.04 | Not established |
| Fully integrated RC2 sources committed to Git | **Pending** |

1.0 must not be tagged until the blocking gates are verified. The upstream `main` branch remains unchanged.

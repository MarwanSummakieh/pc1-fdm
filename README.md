# pc1-fdm

PC1 controller-friendly GPLv3 FDM Classic fork with download and BitTorrent support.

Part of the [PC1 project](https://github.com/users/MarwanSummakieh/projects/3).
[MarwanOS](https://github.com/MarwanSummakieh/MarwanOS) builds the complete OS and
integrates an exact pinned export of this component. This repository owns its
implementation; the Godot UI for backend components lives in pc1-shell.

Source organization date: 2026-10-06. The exported implementation includes the
2026-10-05 development work from MarwanOS commit a634e6ce3001f197524daa8cf357b160383890db.
Existing relative paths are retained so component Python tests can run directly.

See the documentation in docs/ for behavior, evidence and current limitations.
For cross-component tests and complete image builds, use the PC1 OS workspace.
The OS repository's pc1-components.json records the integrated commit and file
ownership; scripts/components.py checks or restores the pinned integration copies.
## Source and build

This is the GPLv3 FDM Classic 3.9.7 fork, retaining upstream history through
1bd57c2f5aef2a06ba51990a876aa3632071630c and the original license/copyright files.
It is separate from closed-source modern FDM. The Classic download engine and
BitTorrent support remain; the controller view is the PC1 portable default.

```bash
g++ -std=c++14 tests/controller-input-test.cpp -o /tmp/pc1-fdm-input
/tmp/pc1-fdm-input
```

The full application is a legacy Windows/MSVC build. build-local.ps1 now points
to this repository's trunc/ tree. It requires the existing MSBuild installation,
downloaded toolchain/sdk folders and Boost dependencies from the development
environment; those generated dependencies and binaries are not committed.
The source-build and bench reports in docs/ record the exact validated setup.
Portable launch currently uses FDM_LOCAL_TEST=1 and FDM_CONTROLLER_UI=1 with
FDM.exe -nelvcheck. Do not deploy a new binary until its transfer/input checks pass.

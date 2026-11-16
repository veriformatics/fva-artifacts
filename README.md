# fva-artifacts

This repository holds files that [FVA](https://github.com/veriformatics/fva) fetches but does not
keep in its own repository. They are third-party build artifacts, inputs whose upstream copies are
gone, and archives of benchmark runs.

Each set of files is one release of this repository. FVA's fetch scripts pin every file by its
SHA-256, so a changed file fails the fetch. Files in a release never change; a new version of a
set is a new release.

## Releases

| Release | Contents | License |
|---|---|---|
| `edger-4.99.10` | The edgeR 4.99.10 package as built for WebAssembly by R-universe (`edgeR_4.99.10.tgz`, which holds `edgeR/libs/edgeR.so`) and its source package (`edgeR_4.99.10.tar.gz`). R-universe removed both files when it moved to edgeR 4.99.12. | GPL-2.0-or-later |
| `subject-builds-v1` | WebAssembly builds of third-party code used by FVA's proofs, tests and benchmark tasks: lz4 C (`-O2`, `-O1`), lz4_flex, GLM `iround`, runorm `pflog`, and FVA's C++ exception example linked with wasi-sdk's runtime. Each file has a notice that names its corresponding source. | BSD-2-Clause, MIT, Apache-2.0 + runtime licenses (per file) |
| `bench-runs-v2-redacted-v1` | The graded benchmark v2 runs with personal machine labels removed, including labels inside compressed event logs. | per run (see `bench/runs/NOTICE` in the archive) |

## Licenses

Each file keeps the license of its upstream project. The notes of each release name the license,
the upstream project, the version and the corresponding source. The license texts are in
[`licenses/`](licenses/).

## Privacy edition

The public benchmark archive removes personal machine labels. It preserves scientific source and input files, license notices, event structure, and numeric results. Historical machine paths remain nonportable. This is a redacted evidence export, not a new benchmark run.

The original archive is retained in a private offline backup. The public edition has a separate release and SHA-256. FVA pins this edition explicitly. Files in the other releases keep their original bytes.

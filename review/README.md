# TomEE 10.3.0 and 11.0.0-M2 — release verification

[Source branch](https://github.com/jenkinsrei-bot-hopper/docker-tomee/tree/tomee-10.3.0-11.0.0-M2) · [Source commit](https://github.com/jenkinsrei-bot-hopper/docker-tomee/commit/8a515bdfb91f554b66e73ac61cdeba3497c4d453)

**Status:** source changes are pushed to the bot fork. No upstream PR was open when this report was prepared. The Official Images repository has not been forked, branched, edited, or submitted to. Its entry recommendations below are a report-only handoff for the maintainer.

## What changed

- Added all 36 `TomEE-10.3/` Dockerfiles for 10.3.0, with the same JRE/vendor/OS/flavor paths and exact base-image references as 10.2.
- Updated all 36 existing `TomEE-11.0/` Dockerfiles from M1 to 11.0.0-M2, preserving their base-image references.
- Kept `TomEE-10.2/` byte-for-byte unchanged.
- Pinned the official per-flavor SHA512 values; imported Apache TomEE KEYS and verified signatures using only the selected release signer’s full fingerprint in a separate keyring.
- Updated README versions, flavors, tag syntax, and local-build examples. It explicitly distinguishes source releases from independently published registry tags.

The signing-key fingerprint is `85FBBE98D6C37CDA8A7D8FF9F9FF83A48D339D37` (Markus Jung). All eight complete release archives passed SHA512, detached signature, expected signer, and archive-root checks. See [all verification values and source URLs](release-verification.csv), the official [10.3.0 release directory](https://downloads.apache.org/tomee/tomee-10.3.0/), [M2 release directory](https://downloads.apache.org/tomee/tomee-11.0.0-M2/), and [Apache KEYS](https://downloads.apache.org/tomee/KEYS).

## Added directories

The new tree has 36 image-variant directories: JRE 17/21/25 × Temurin (Alpine/Ubuntu) or Semeru (Ubuntu) × webprofile/microprofile/plus/plume. The [complete 36-variant list](added-directories.txt) gives every Dockerfile directory; the [complete 55-directory list including parents](added-directories-all.txt) gives the literal new directory tree.

## Local builds and startup checks

All six Linux/amd64 JRE 17 webprofile images below built successfully and served HTTP 200 at `/`. Each build executed the actual download, pinned SHA512, pinned-key GPG verification, extraction, and cleanup instructions.

| Release | Vendor / OS | Build | HTTP startup |
| --- | --- | --- | --- |
| 10.3.0 | Semeru / ubuntu | PASS | 200 |
| 10.3.0 | Temurin / alpine | PASS | 200 |
| 10.3.0 | Temurin / ubuntu | PASS | 200 |
| 11.0.0-M2 | Semeru / ubuntu | PASS | 200 |
| 11.0.0-M2 | Temurin / alpine | PASS | 200 |
| 11.0.0-M2 | Temurin / ubuntu | PASS | 200 |

The nested sandbox does not expose a usable rootless TUN device or systemd user bus. Startup checks therefore used standard Podman host networking with `--cgroup-manager=cgroupfs --cgroups=disabled`; the images themselves were not changed. Builds used Buildah VFS/chroot mode. [Exact results](build-results.csv) and [build/startup logs](build-logs/) are included. JRE 21/25, arm64, and every flavor were not individually image-built; all eight flavor archives were cryptographically verified.

## Official Images tag handoff

The current tag authority is Docker Official Images [library/tomee](https://github.com/docker-library/official-images/blob/master/library/tomee). Default omitted components are JRE 25, Temurin, Ubuntu, and microprofile. This report preserves that alias expansion pattern.

| Current tag family | Proposed owner / action |
| --- | --- |
| Exact `10.2.0` tags | Stay on the unchanged 10.2 source and old commit. |
| Existing `10.1` minor aliases | Currently point to 10.2; recommended to retain for compatibility pending a maintainer decision. |
| Correct `10.2` minor aliases | Add to the unchanged 10.2 entries to repair the missing minor aliases. |
| Full `10.3.0` and minor `10.3` tags | New 10.3 entries. |
| All `10` major aliases, bare JRE/vendor/OS/flavor aliases, and `latest` | Move from 10.2 to 10.3: 320 explicitly listed aliases. |
| Exact `11.0.0-M1` tags | Stay pinned to the old source commit, even though the current 11.0 directory is updated. |
| Full `11.0.0-M2` tags | New M2 entries. |
| `11.0` and `11` aliases | Move from M1 to M2: 320 explicitly listed aliases. No milestone gets `latest` or unversioned aliases. |

The [complete 72-row current-versus-proposed table](tag-comparison.csv) includes every original, retained, new, and moved alias, plus each Directory, GitCommit, and architecture value. [Expanded readable lists](tag-comparison.md) and [all 144 exact entry blocks](official-images-entry-handoff.txt) accompany it. All 1,120 original tag occurrences remain represented exactly once; the proposed split has no duplicate tags. JRE 17 Temurin Alpine remains amd64-only; other current entries retain amd64/arm64v8.

**GitCommit handoff:** retained 10.2 and M1 entries use `3695dcec008bf611b2dbd06eb2123a7b159efc27`. New 10.3 and M2 entries currently show source candidate `8a515bdfb91f554b66e73ac61cdeba3497c4d453`. `GitRepo` must remain `https://github.com/tomitribe/docker-tomee.git`. Do not file the handoff until this source is merged and the chosen hash is reachable upstream. A normal merge may preserve the candidate hash; if squash/rebase changes it, replace new-entry hashes with the resulting upstream source commit. This is the only merge-dependent value.

## Review and open question

Source PR review and Official Images submission are separate steps. These report-only artifacts do not move registry tags.

**Legacy-alias decision:** the current 10.2 entries accidentally carry `10.1` minor aliases. The report recommends keeping those aliases where they are for compatibility and adding proper `10.2` aliases. Do you want that compatibility-preserving approach, or a separate cleanup? This does not block the source PR.

Both source and report commits use `[skip ci]`; the source repository contains no CI configuration, and the bot fork had no Actions runs after its source push. No upstream CI was invoked.

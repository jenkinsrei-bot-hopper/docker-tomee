# TomEE 10.3.0 and 11.0.0-M2 — ready for Bob’s recheck

[Source branch](https://github.com/jenkinsrei-bot-hopper/docker-tomee/tree/tomee-10.3.0-11.0.0-M2) · [Source commit 78b8b8e](https://github.com/jenkinsrei-bot-hopper/docker-tomee/commit/78b8b8e777df44091537d5f2e1fe7ad3d9359f3f)

The requested minimal correction is pushed to the bot fork. **No PR has been opened; Bob’s explicit approval is still required.** This review directory is report-only; use the source commit above for code review. The Official Images repository has not been forked, branched, edited, or submitted to.

## Minimal source changes

All 36 new `TomEE-10.3/` Dockerfiles are byte-for-byte copies of their `TomEE-10.2/` counterparts except for `TOMEE_VER=10.2.0` → `10.3.0`. All 36 `TomEE-11.0/` Dockerfiles differ from upstream master only by `TOMEE_VER=11.0.0-M1` → `11.0.0-M2`. Base images, download mirrors/fallbacks, checksum and GPG commands, key lists, formatting, and cleanup are unchanged. `TomEE-10.2/` is byte-for-byte unchanged.

The README has only four line substitutions: two version-description lines and its existing tag example at both occurrences. Every other line is retained. Independent final-tree review against upstream master passed these exact-copy checks.

The [full `git diff --stat upstream/master HEAD`](source-diff-stat.txt) is **73 files changed, 3,508 insertions, 40 deletions**: 36 added Dockerfiles, 36 version-only modifications, and README. Copied whitespace and final blank lines inherited from 10.2 were deliberately preserved.

The existing key list already includes Markus Jung’s fingerprint, `85FBBE98D6C37CDA8A7D8FF9F9FF83A48D339D37`. The retained recipe downloads and checks the published SHA512 file and detached GPG signature. All eight release archives were separately verified in the earlier release check; [the exact values and source URLs](release-verification.csv) remain available. Official sources: [10.3.0](https://downloads.apache.org/tomee/tomee-10.3.0/), [11.0.0-M2](https://downloads.apache.org/tomee/tomee-11.0.0-M2/), and [Apache KEYS](https://downloads.apache.org/tomee/KEYS). No verification hardening is included in the source branch; an [optional follow-up proposal](verification-hardening-proposal.md) is separate.

## Added directories

The new tree has 36 image-variant directories: JRE 17/21/25 × Temurin (Alpine/Ubuntu) or Semeru (Ubuntu) × webprofile/microprofile/plus/plume. The [complete 36-variant list](added-directories.txt) gives every Dockerfile directory; the [complete 55-directory list including parents](added-directories-all.txt) gives the literal new directory tree. Both lists were checked against the final source tree.

## Fresh local builds and startup checks

All three vendor/OS combinations were rebuilt for both releases from source commit `78b8b8e777df44091537d5f2e1fe7ad3d9359f3f`. These six Linux/amd64 JRE 17 webprofile builds used no cache and pulled the base images. Each completed the original download, SHA512, GPG verification, extraction, and cleanup instructions, then served HTTP 200 at `/`.

| Release | Vendor / OS | Build | HTTP startup |
| --- | --- | --- | --- |
| 10.3.0 | Temurin / alpine | PASS | 200 |
| 10.3.0 | Temurin / ubuntu | PASS | 200 |
| 10.3.0 | Semeru / ubuntu | PASS | 200 |
| 11.0.0-M2 | Temurin / alpine | PASS | 200 |
| 11.0.0-M2 | Temurin / ubuntu | PASS | 200 |
| 11.0.0-M2 | Semeru / ubuntu | PASS | 200 |

The first default Podman attempts stopped at the sandbox’s unavailable systemd user bus. The successful rerun used Buildah VFS/chroot mode and Podman host networking with `--cgroup-manager=cgroupfs --cgroups=disabled`; the Dockerfiles were not changed for this workaround. [Exact results with source provenance](build-results.csv) and [fresh build/startup logs](build-logs/) are included. JRE 21/25, arm64, and non-webprofile images were not individually built; all eight flavor archives were cryptographically verified separately.

## Official Images tag handoff

The tag authority is Docker Official Images [library/tomee](https://github.com/docker-library/official-images/blob/master/library/tomee). Default omitted components remain JRE 25, Temurin, Ubuntu, and microprofile.

| Current tag family | Proposed owner / action |
| --- | --- |
| Exact `10.2.0` tags | Stay on the unchanged 10.2 source and old commit. |
| Existing `10.1` minor aliases | Currently point to 10.2; retain for compatibility pending Rod’s decision. |
| Correct `10.2` minor aliases | Add to the unchanged 10.2 entries to repair the missing minor aliases. |
| Full `10.3.0` and minor `10.3` tags | New 10.3 entries. |
| All `10` major aliases, bare JRE/vendor/OS/flavor aliases, and `latest` | Move from 10.2 to 10.3: 320 explicitly listed aliases. |
| Exact `11.0.0-M1` tags | Stay pinned to the old source commit. |
| Full `11.0.0-M2` tags | New M2 entries. |
| `11.0` and `11` aliases | Move from M1 to M2: 320 explicitly listed aliases. No milestone gets `latest` or unversioned aliases. |

The [complete 72-row comparison](tag-comparison.csv) contains every original, retained, new, and moved alias, plus Directory, GitCommit, and architectures. [Expanded readable lists](tag-comparison.md) and [all 144 exact entry blocks](official-images-entry-handoff.txt) accompany it. All 1,120 original tag occurrences remain represented exactly once; the proposed 1,760 unique tags have no duplicates. JRE 17 Temurin Alpine remains amd64-only; other entries retain amd64/arm64v8.

**GitCommit handoff:** retained 10.2 and M1 entries use `3695dcec008bf611b2dbd06eb2123a7b159efc27`. All 72 new 10.3/M2 blocks now use source candidate `78b8b8e777df44091537d5f2e1fe7ad3d9359f3f`. `GitRepo` must remain `https://github.com/tomitribe/docker-tomee.git`. Do not submit the handoff until the source is merged and the hash is reachable upstream. If squash/rebase changes the source hash, replace the new-entry hashes with the resulting upstream source commit.

## Decisions still needed

Bob must recheck the source branch and explicitly authorize any PR. Rod’s separate legacy-alias decision remains open: keep existing `10.1` aliases on 10.2 for compatibility and add proper `10.2` aliases, or handle them in a separate cleanup? This does not block source review, and the report does not itself move registry tags.

Both correction and report commits use `[skip ci]`. The source tree has no CI configuration, the bot fork had zero Actions runs after the source push, and no upstream CI was invoked.

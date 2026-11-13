# TomEE Docker tag comparison and official-images handoff

Candidate source commit: `8a515bdfb91f554b66e73ac61cdeba3497c4d453`. Verify upstream reachability after merge before filing.
Current snapshot GitCommit for retained entries: `3695dcec008bf611b2dbd06eb2123a7b159efc27` for 10.2; `3695dcec008bf611b2dbd06eb2123a7b159efc27` for M1.

**Summary:** 72 flavors; 36 new release directories; 1120 original tag occurrences; 640 unique moved aliases; 640 retained tag entries and 1120 new tag entries. The 72-row CSV includes the complete unabridged tag lists for every flavor.

## Policy and cautions

- TomEE 10.3 receives full `10.3.0` and minor `10.3` tags; all `10` major and unversioned aliases (including `latest`) move from 10.2 to 10.3.
- Keep 10.2.0 full tags and the legacy 10.1 minor aliases on the unchanged 10.2 entries; add the proper 10.2 minor aliases there. The legacy 10.1-on-10.2 mapping is an anomaly for the maintainer to accept explicitly; it is not silently moved or removed.
- TomEE 11.0.0-M2 receives full M2 tags and moving `11.0`/`11` aliases. Keep exact M1 tags at the old commit; never put `latest` or unversioned aliases on M2.
- `latest` and unversioned tags are deliberately moved to 10.3 only. Proposed final tags have no duplicates.
- Default architectures remain `amd64, arm64v8`; the four JRE 17 Temurin Alpine flavors explicitly override to `amd64` on both retained and new release entries.
- Handoff is report-only, not a ready-to-copy library file. New GitCommit must be reachable from upstream `tomitribe/docker-tomee.git` after merge. If squash/rebase changes the hash, rerun this generator with the reachable final 40-hex hash. The candidate hash is for review until it is reachable from upstream after merge.

## Complete flavor comparison

### 10_2_to_10_3 — TomEE-10.2/jre25/Temurin/ubuntu/microprofile

- Original tags: 10.2.0-jre25-Temurin-ubuntu-microprofile;10.2.0-Temurin-ubuntu-microprofile;10.2.0-jre25-ubuntu-microprofile;10.2.0-ubuntu-microprofile;10.2.0-jre25-Temurin-microprofile;10.2.0-Temurin-microprofile;10.2.0-jre25-microprofile;10.2.0-microprofile;10.2.0-jre25-Temurin-ubuntu;10.2.0-Temurin-ubuntu;10.2.0-jre25-ubuntu;10.2.0-ubuntu;10.2.0-jre25-Temurin;10.2.0-Temurin;10.2.0-jre25;10.2.0;10.1-jre25-Temurin-ubuntu-microprofile;10.1-Temurin-ubuntu-microprofile;10.1-jre25-ubuntu-microprofile;10.1-ubuntu-microprofile;10.1-jre25-Temurin-microprofile;10.1-Temurin-microprofile;10.1-jre25-microprofile;10.1-microprofile;10.1-jre25-Temurin-ubuntu;10.1-Temurin-ubuntu;10.1-jre25-ubuntu;10.1-ubuntu;10.1-jre25-Temurin;10.1-Temurin;10.1-jre25;10.1;10-jre25-Temurin-ubuntu-microprofile;10-Temurin-ubuntu-microprofile;10-jre25-ubuntu-microprofile;10-ubuntu-microprofile;10-jre25-Temurin-microprofile;10-Temurin-microprofile;10-jre25-microprofile;10-microprofile;10-jre25-Temurin-ubuntu;10-Temurin-ubuntu;10-jre25-ubuntu;10-ubuntu;10-jre25-Temurin;10-Temurin;10-jre25;10;jre25-Temurin-ubuntu-microprofile;Temurin-ubuntu-microprofile;jre25-ubuntu-microprofile;ubuntu-microprofile;jre25-Temurin-microprofile;Temurin-microprofile;jre25-microprofile;microprofile;jre25-Temurin-ubuntu;Temurin-ubuntu;jre25-ubuntu;ubuntu;jre25-Temurin;Temurin;jre25;latest
- Retained tags: 10.2.0-jre25-Temurin-ubuntu-microprofile;10.2.0-Temurin-ubuntu-microprofile;10.2.0-jre25-ubuntu-microprofile;10.2.0-ubuntu-microprofile;10.2.0-jre25-Temurin-microprofile;10.2.0-Temurin-microprofile;10.2.0-jre25-microprofile;10.2.0-microprofile;10.2.0-jre25-Temurin-ubuntu;10.2.0-Temurin-ubuntu;10.2.0-jre25-ubuntu;10.2.0-ubuntu;10.2.0-jre25-Temurin;10.2.0-Temurin;10.2.0-jre25;10.2.0;10.1-jre25-Temurin-ubuntu-microprofile;10.1-Temurin-ubuntu-microprofile;10.1-jre25-ubuntu-microprofile;10.1-ubuntu-microprofile;10.1-jre25-Temurin-microprofile;10.1-Temurin-microprofile;10.1-jre25-microprofile;10.1-microprofile;10.1-jre25-Temurin-ubuntu;10.1-Temurin-ubuntu;10.1-jre25-ubuntu;10.1-ubuntu;10.1-jre25-Temurin;10.1-Temurin;10.1-jre25;10.1;10.2-jre25-Temurin-ubuntu-microprofile;10.2-Temurin-ubuntu-microprofile;10.2-jre25-ubuntu-microprofile;10.2-ubuntu-microprofile;10.2-jre25-Temurin-microprofile;10.2-Temurin-microprofile;10.2-jre25-microprofile;10.2-microprofile;10.2-jre25-Temurin-ubuntu;10.2-Temurin-ubuntu;10.2-jre25-ubuntu;10.2-ubuntu;10.2-jre25-Temurin;10.2-Temurin;10.2-jre25;10.2
- New tags: 10.3.0-jre25-Temurin-ubuntu-microprofile;10.3.0-Temurin-ubuntu-microprofile;10.3.0-jre25-ubuntu-microprofile;10.3.0-ubuntu-microprofile;10.3.0-jre25-Temurin-microprofile;10.3.0-Temurin-microprofile;10.3.0-jre25-microprofile;10.3.0-microprofile;10.3.0-jre25-Temurin-ubuntu;10.3.0-Temurin-ubuntu;10.3.0-jre25-ubuntu;10.3.0-ubuntu;10.3.0-jre25-Temurin;10.3.0-Temurin;10.3.0-jre25;10.3.0;10.3-jre25-Temurin-ubuntu-microprofile;10.3-Temurin-ubuntu-microprofile;10.3-jre25-ubuntu-microprofile;10.3-ubuntu-microprofile;10.3-jre25-Temurin-microprofile;10.3-Temurin-microprofile;10.3-jre25-microprofile;10.3-microprofile;10.3-jre25-Temurin-ubuntu;10.3-Temurin-ubuntu;10.3-jre25-ubuntu;10.3-ubuntu;10.3-jre25-Temurin;10.3-Temurin;10.3-jre25;10.3;10-jre25-Temurin-ubuntu-microprofile;10-Temurin-ubuntu-microprofile;10-jre25-ubuntu-microprofile;10-ubuntu-microprofile;10-jre25-Temurin-microprofile;10-Temurin-microprofile;10-jre25-microprofile;10-microprofile;10-jre25-Temurin-ubuntu;10-Temurin-ubuntu;10-jre25-ubuntu;10-ubuntu;10-jre25-Temurin;10-Temurin;10-jre25;10;jre25-Temurin-ubuntu-microprofile;Temurin-ubuntu-microprofile;jre25-ubuntu-microprofile;ubuntu-microprofile;jre25-Temurin-microprofile;Temurin-microprofile;jre25-microprofile;microprofile;jre25-Temurin-ubuntu;Temurin-ubuntu;jre25-ubuntu;ubuntu;jre25-Temurin;Temurin;jre25;latest
- Explicit moved aliases: 10-jre25-Temurin-ubuntu-microprofile;10-Temurin-ubuntu-microprofile;10-jre25-ubuntu-microprofile;10-ubuntu-microprofile;10-jre25-Temurin-microprofile;10-Temurin-microprofile;10-jre25-microprofile;10-microprofile;10-jre25-Temurin-ubuntu;10-Temurin-ubuntu;10-jre25-ubuntu;10-ubuntu;10-jre25-Temurin;10-Temurin;10-jre25;10;jre25-Temurin-ubuntu-microprofile;Temurin-ubuntu-microprofile;jre25-ubuntu-microprofile;ubuntu-microprofile;jre25-Temurin-microprofile;Temurin-microprofile;jre25-microprofile;microprofile;jre25-Temurin-ubuntu;Temurin-ubuntu;jre25-ubuntu;ubuntu;jre25-Temurin;Temurin;jre25;latest
- Directories: `TomEE-10.2/jre25/Temurin/ubuntu/microprofile` → `TomEE-10.3/jre25/Temurin/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Temurin/ubuntu/plume

- Original tags: 10.2.0-jre25-Temurin-ubuntu-plume;10.2.0-Temurin-ubuntu-plume;10.2.0-jre25-ubuntu-plume;10.2.0-ubuntu-plume;10.2.0-jre25-Temurin-plume;10.2.0-Temurin-plume;10.2.0-jre25-plume;10.2.0-plume;10.1-jre25-Temurin-ubuntu-plume;10.1-Temurin-ubuntu-plume;10.1-jre25-ubuntu-plume;10.1-ubuntu-plume;10.1-jre25-Temurin-plume;10.1-Temurin-plume;10.1-jre25-plume;10.1-plume;10-jre25-Temurin-ubuntu-plume;10-Temurin-ubuntu-plume;10-jre25-ubuntu-plume;10-ubuntu-plume;10-jre25-Temurin-plume;10-Temurin-plume;10-jre25-plume;10-plume;jre25-Temurin-ubuntu-plume;Temurin-ubuntu-plume;jre25-ubuntu-plume;ubuntu-plume;jre25-Temurin-plume;Temurin-plume;jre25-plume;plume
- Retained tags: 10.2.0-jre25-Temurin-ubuntu-plume;10.2.0-Temurin-ubuntu-plume;10.2.0-jre25-ubuntu-plume;10.2.0-ubuntu-plume;10.2.0-jre25-Temurin-plume;10.2.0-Temurin-plume;10.2.0-jre25-plume;10.2.0-plume;10.1-jre25-Temurin-ubuntu-plume;10.1-Temurin-ubuntu-plume;10.1-jre25-ubuntu-plume;10.1-ubuntu-plume;10.1-jre25-Temurin-plume;10.1-Temurin-plume;10.1-jre25-plume;10.1-plume;10.2-jre25-Temurin-ubuntu-plume;10.2-Temurin-ubuntu-plume;10.2-jre25-ubuntu-plume;10.2-ubuntu-plume;10.2-jre25-Temurin-plume;10.2-Temurin-plume;10.2-jre25-plume;10.2-plume
- New tags: 10.3.0-jre25-Temurin-ubuntu-plume;10.3.0-Temurin-ubuntu-plume;10.3.0-jre25-ubuntu-plume;10.3.0-ubuntu-plume;10.3.0-jre25-Temurin-plume;10.3.0-Temurin-plume;10.3.0-jre25-plume;10.3.0-plume;10.3-jre25-Temurin-ubuntu-plume;10.3-Temurin-ubuntu-plume;10.3-jre25-ubuntu-plume;10.3-ubuntu-plume;10.3-jre25-Temurin-plume;10.3-Temurin-plume;10.3-jre25-plume;10.3-plume;10-jre25-Temurin-ubuntu-plume;10-Temurin-ubuntu-plume;10-jre25-ubuntu-plume;10-ubuntu-plume;10-jre25-Temurin-plume;10-Temurin-plume;10-jre25-plume;10-plume;jre25-Temurin-ubuntu-plume;Temurin-ubuntu-plume;jre25-ubuntu-plume;ubuntu-plume;jre25-Temurin-plume;Temurin-plume;jre25-plume;plume
- Explicit moved aliases: 10-jre25-Temurin-ubuntu-plume;10-Temurin-ubuntu-plume;10-jre25-ubuntu-plume;10-ubuntu-plume;10-jre25-Temurin-plume;10-Temurin-plume;10-jre25-plume;10-plume;jre25-Temurin-ubuntu-plume;Temurin-ubuntu-plume;jre25-ubuntu-plume;ubuntu-plume;jre25-Temurin-plume;Temurin-plume;jre25-plume;plume
- Directories: `TomEE-10.2/jre25/Temurin/ubuntu/plume` → `TomEE-10.3/jre25/Temurin/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Temurin/ubuntu/plus

- Original tags: 10.2.0-jre25-Temurin-ubuntu-plus;10.2.0-Temurin-ubuntu-plus;10.2.0-jre25-ubuntu-plus;10.2.0-ubuntu-plus;10.2.0-jre25-Temurin-plus;10.2.0-Temurin-plus;10.2.0-jre25-plus;10.2.0-plus;10.1-jre25-Temurin-ubuntu-plus;10.1-Temurin-ubuntu-plus;10.1-jre25-ubuntu-plus;10.1-ubuntu-plus;10.1-jre25-Temurin-plus;10.1-Temurin-plus;10.1-jre25-plus;10.1-plus;10-jre25-Temurin-ubuntu-plus;10-Temurin-ubuntu-plus;10-jre25-ubuntu-plus;10-ubuntu-plus;10-jre25-Temurin-plus;10-Temurin-plus;10-jre25-plus;10-plus;jre25-Temurin-ubuntu-plus;Temurin-ubuntu-plus;jre25-ubuntu-plus;ubuntu-plus;jre25-Temurin-plus;Temurin-plus;jre25-plus;plus
- Retained tags: 10.2.0-jre25-Temurin-ubuntu-plus;10.2.0-Temurin-ubuntu-plus;10.2.0-jre25-ubuntu-plus;10.2.0-ubuntu-plus;10.2.0-jre25-Temurin-plus;10.2.0-Temurin-plus;10.2.0-jre25-plus;10.2.0-plus;10.1-jre25-Temurin-ubuntu-plus;10.1-Temurin-ubuntu-plus;10.1-jre25-ubuntu-plus;10.1-ubuntu-plus;10.1-jre25-Temurin-plus;10.1-Temurin-plus;10.1-jre25-plus;10.1-plus;10.2-jre25-Temurin-ubuntu-plus;10.2-Temurin-ubuntu-plus;10.2-jre25-ubuntu-plus;10.2-ubuntu-plus;10.2-jre25-Temurin-plus;10.2-Temurin-plus;10.2-jre25-plus;10.2-plus
- New tags: 10.3.0-jre25-Temurin-ubuntu-plus;10.3.0-Temurin-ubuntu-plus;10.3.0-jre25-ubuntu-plus;10.3.0-ubuntu-plus;10.3.0-jre25-Temurin-plus;10.3.0-Temurin-plus;10.3.0-jre25-plus;10.3.0-plus;10.3-jre25-Temurin-ubuntu-plus;10.3-Temurin-ubuntu-plus;10.3-jre25-ubuntu-plus;10.3-ubuntu-plus;10.3-jre25-Temurin-plus;10.3-Temurin-plus;10.3-jre25-plus;10.3-plus;10-jre25-Temurin-ubuntu-plus;10-Temurin-ubuntu-plus;10-jre25-ubuntu-plus;10-ubuntu-plus;10-jre25-Temurin-plus;10-Temurin-plus;10-jre25-plus;10-plus;jre25-Temurin-ubuntu-plus;Temurin-ubuntu-plus;jre25-ubuntu-plus;ubuntu-plus;jre25-Temurin-plus;Temurin-plus;jre25-plus;plus
- Explicit moved aliases: 10-jre25-Temurin-ubuntu-plus;10-Temurin-ubuntu-plus;10-jre25-ubuntu-plus;10-ubuntu-plus;10-jre25-Temurin-plus;10-Temurin-plus;10-jre25-plus;10-plus;jre25-Temurin-ubuntu-plus;Temurin-ubuntu-plus;jre25-ubuntu-plus;ubuntu-plus;jre25-Temurin-plus;Temurin-plus;jre25-plus;plus
- Directories: `TomEE-10.2/jre25/Temurin/ubuntu/plus` → `TomEE-10.3/jre25/Temurin/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Temurin/ubuntu/webprofile

- Original tags: 10.2.0-jre25-Temurin-ubuntu-webprofile;10.2.0-Temurin-ubuntu-webprofile;10.2.0-jre25-ubuntu-webprofile;10.2.0-ubuntu-webprofile;10.2.0-jre25-Temurin-webprofile;10.2.0-Temurin-webprofile;10.2.0-jre25-webprofile;10.2.0-webprofile;10.1-jre25-Temurin-ubuntu-webprofile;10.1-Temurin-ubuntu-webprofile;10.1-jre25-ubuntu-webprofile;10.1-ubuntu-webprofile;10.1-jre25-Temurin-webprofile;10.1-Temurin-webprofile;10.1-jre25-webprofile;10.1-webprofile;10-jre25-Temurin-ubuntu-webprofile;10-Temurin-ubuntu-webprofile;10-jre25-ubuntu-webprofile;10-ubuntu-webprofile;10-jre25-Temurin-webprofile;10-Temurin-webprofile;10-jre25-webprofile;10-webprofile;jre25-Temurin-ubuntu-webprofile;Temurin-ubuntu-webprofile;jre25-ubuntu-webprofile;ubuntu-webprofile;jre25-Temurin-webprofile;Temurin-webprofile;jre25-webprofile;webprofile
- Retained tags: 10.2.0-jre25-Temurin-ubuntu-webprofile;10.2.0-Temurin-ubuntu-webprofile;10.2.0-jre25-ubuntu-webprofile;10.2.0-ubuntu-webprofile;10.2.0-jre25-Temurin-webprofile;10.2.0-Temurin-webprofile;10.2.0-jre25-webprofile;10.2.0-webprofile;10.1-jre25-Temurin-ubuntu-webprofile;10.1-Temurin-ubuntu-webprofile;10.1-jre25-ubuntu-webprofile;10.1-ubuntu-webprofile;10.1-jre25-Temurin-webprofile;10.1-Temurin-webprofile;10.1-jre25-webprofile;10.1-webprofile;10.2-jre25-Temurin-ubuntu-webprofile;10.2-Temurin-ubuntu-webprofile;10.2-jre25-ubuntu-webprofile;10.2-ubuntu-webprofile;10.2-jre25-Temurin-webprofile;10.2-Temurin-webprofile;10.2-jre25-webprofile;10.2-webprofile
- New tags: 10.3.0-jre25-Temurin-ubuntu-webprofile;10.3.0-Temurin-ubuntu-webprofile;10.3.0-jre25-ubuntu-webprofile;10.3.0-ubuntu-webprofile;10.3.0-jre25-Temurin-webprofile;10.3.0-Temurin-webprofile;10.3.0-jre25-webprofile;10.3.0-webprofile;10.3-jre25-Temurin-ubuntu-webprofile;10.3-Temurin-ubuntu-webprofile;10.3-jre25-ubuntu-webprofile;10.3-ubuntu-webprofile;10.3-jre25-Temurin-webprofile;10.3-Temurin-webprofile;10.3-jre25-webprofile;10.3-webprofile;10-jre25-Temurin-ubuntu-webprofile;10-Temurin-ubuntu-webprofile;10-jre25-ubuntu-webprofile;10-ubuntu-webprofile;10-jre25-Temurin-webprofile;10-Temurin-webprofile;10-jre25-webprofile;10-webprofile;jre25-Temurin-ubuntu-webprofile;Temurin-ubuntu-webprofile;jre25-ubuntu-webprofile;ubuntu-webprofile;jre25-Temurin-webprofile;Temurin-webprofile;jre25-webprofile;webprofile
- Explicit moved aliases: 10-jre25-Temurin-ubuntu-webprofile;10-Temurin-ubuntu-webprofile;10-jre25-ubuntu-webprofile;10-ubuntu-webprofile;10-jre25-Temurin-webprofile;10-Temurin-webprofile;10-jre25-webprofile;10-webprofile;jre25-Temurin-ubuntu-webprofile;Temurin-ubuntu-webprofile;jre25-ubuntu-webprofile;ubuntu-webprofile;jre25-Temurin-webprofile;Temurin-webprofile;jre25-webprofile;webprofile
- Directories: `TomEE-10.2/jre25/Temurin/ubuntu/webprofile` → `TomEE-10.3/jre25/Temurin/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Temurin/alpine/microprofile

- Original tags: 10.2.0-jre25-Temurin-alpine-microprofile;10.2.0-Temurin-alpine-microprofile;10.2.0-jre25-alpine-microprofile;10.2.0-alpine-microprofile;10.2.0-jre25-Temurin-alpine;10.2.0-Temurin-alpine;10.2.0-jre25-alpine;10.2.0-alpine;10.1-jre25-Temurin-alpine-microprofile;10.1-Temurin-alpine-microprofile;10.1-jre25-alpine-microprofile;10.1-alpine-microprofile;10.1-jre25-Temurin-alpine;10.1-Temurin-alpine;10.1-jre25-alpine;10.1-alpine;10-jre25-Temurin-alpine-microprofile;10-Temurin-alpine-microprofile;10-jre25-alpine-microprofile;10-alpine-microprofile;10-jre25-Temurin-alpine;10-Temurin-alpine;10-jre25-alpine;10-alpine;jre25-Temurin-alpine-microprofile;Temurin-alpine-microprofile;jre25-alpine-microprofile;alpine-microprofile;jre25-Temurin-alpine;Temurin-alpine;jre25-alpine;alpine
- Retained tags: 10.2.0-jre25-Temurin-alpine-microprofile;10.2.0-Temurin-alpine-microprofile;10.2.0-jre25-alpine-microprofile;10.2.0-alpine-microprofile;10.2.0-jre25-Temurin-alpine;10.2.0-Temurin-alpine;10.2.0-jre25-alpine;10.2.0-alpine;10.1-jre25-Temurin-alpine-microprofile;10.1-Temurin-alpine-microprofile;10.1-jre25-alpine-microprofile;10.1-alpine-microprofile;10.1-jre25-Temurin-alpine;10.1-Temurin-alpine;10.1-jre25-alpine;10.1-alpine;10.2-jre25-Temurin-alpine-microprofile;10.2-Temurin-alpine-microprofile;10.2-jre25-alpine-microprofile;10.2-alpine-microprofile;10.2-jre25-Temurin-alpine;10.2-Temurin-alpine;10.2-jre25-alpine;10.2-alpine
- New tags: 10.3.0-jre25-Temurin-alpine-microprofile;10.3.0-Temurin-alpine-microprofile;10.3.0-jre25-alpine-microprofile;10.3.0-alpine-microprofile;10.3.0-jre25-Temurin-alpine;10.3.0-Temurin-alpine;10.3.0-jre25-alpine;10.3.0-alpine;10.3-jre25-Temurin-alpine-microprofile;10.3-Temurin-alpine-microprofile;10.3-jre25-alpine-microprofile;10.3-alpine-microprofile;10.3-jre25-Temurin-alpine;10.3-Temurin-alpine;10.3-jre25-alpine;10.3-alpine;10-jre25-Temurin-alpine-microprofile;10-Temurin-alpine-microprofile;10-jre25-alpine-microprofile;10-alpine-microprofile;10-jre25-Temurin-alpine;10-Temurin-alpine;10-jre25-alpine;10-alpine;jre25-Temurin-alpine-microprofile;Temurin-alpine-microprofile;jre25-alpine-microprofile;alpine-microprofile;jre25-Temurin-alpine;Temurin-alpine;jre25-alpine;alpine
- Explicit moved aliases: 10-jre25-Temurin-alpine-microprofile;10-Temurin-alpine-microprofile;10-jre25-alpine-microprofile;10-alpine-microprofile;10-jre25-Temurin-alpine;10-Temurin-alpine;10-jre25-alpine;10-alpine;jre25-Temurin-alpine-microprofile;Temurin-alpine-microprofile;jre25-alpine-microprofile;alpine-microprofile;jre25-Temurin-alpine;Temurin-alpine;jre25-alpine;alpine
- Directories: `TomEE-10.2/jre25/Temurin/alpine/microprofile` → `TomEE-10.3/jre25/Temurin/alpine/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Temurin/alpine/plume

- Original tags: 10.2.0-jre25-Temurin-alpine-plume;10.2.0-Temurin-alpine-plume;10.2.0-jre25-alpine-plume;10.2.0-alpine-plume;10.1-jre25-Temurin-alpine-plume;10.1-Temurin-alpine-plume;10.1-jre25-alpine-plume;10.1-alpine-plume;10-jre25-Temurin-alpine-plume;10-Temurin-alpine-plume;10-jre25-alpine-plume;10-alpine-plume;jre25-Temurin-alpine-plume;Temurin-alpine-plume;jre25-alpine-plume;alpine-plume
- Retained tags: 10.2.0-jre25-Temurin-alpine-plume;10.2.0-Temurin-alpine-plume;10.2.0-jre25-alpine-plume;10.2.0-alpine-plume;10.1-jre25-Temurin-alpine-plume;10.1-Temurin-alpine-plume;10.1-jre25-alpine-plume;10.1-alpine-plume;10.2-jre25-Temurin-alpine-plume;10.2-Temurin-alpine-plume;10.2-jre25-alpine-plume;10.2-alpine-plume
- New tags: 10.3.0-jre25-Temurin-alpine-plume;10.3.0-Temurin-alpine-plume;10.3.0-jre25-alpine-plume;10.3.0-alpine-plume;10.3-jre25-Temurin-alpine-plume;10.3-Temurin-alpine-plume;10.3-jre25-alpine-plume;10.3-alpine-plume;10-jre25-Temurin-alpine-plume;10-Temurin-alpine-plume;10-jre25-alpine-plume;10-alpine-plume;jre25-Temurin-alpine-plume;Temurin-alpine-plume;jre25-alpine-plume;alpine-plume
- Explicit moved aliases: 10-jre25-Temurin-alpine-plume;10-Temurin-alpine-plume;10-jre25-alpine-plume;10-alpine-plume;jre25-Temurin-alpine-plume;Temurin-alpine-plume;jre25-alpine-plume;alpine-plume
- Directories: `TomEE-10.2/jre25/Temurin/alpine/plume` → `TomEE-10.3/jre25/Temurin/alpine/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Temurin/alpine/plus

- Original tags: 10.2.0-jre25-Temurin-alpine-plus;10.2.0-Temurin-alpine-plus;10.2.0-jre25-alpine-plus;10.2.0-alpine-plus;10.1-jre25-Temurin-alpine-plus;10.1-Temurin-alpine-plus;10.1-jre25-alpine-plus;10.1-alpine-plus;10-jre25-Temurin-alpine-plus;10-Temurin-alpine-plus;10-jre25-alpine-plus;10-alpine-plus;jre25-Temurin-alpine-plus;Temurin-alpine-plus;jre25-alpine-plus;alpine-plus
- Retained tags: 10.2.0-jre25-Temurin-alpine-plus;10.2.0-Temurin-alpine-plus;10.2.0-jre25-alpine-plus;10.2.0-alpine-plus;10.1-jre25-Temurin-alpine-plus;10.1-Temurin-alpine-plus;10.1-jre25-alpine-plus;10.1-alpine-plus;10.2-jre25-Temurin-alpine-plus;10.2-Temurin-alpine-plus;10.2-jre25-alpine-plus;10.2-alpine-plus
- New tags: 10.3.0-jre25-Temurin-alpine-plus;10.3.0-Temurin-alpine-plus;10.3.0-jre25-alpine-plus;10.3.0-alpine-plus;10.3-jre25-Temurin-alpine-plus;10.3-Temurin-alpine-plus;10.3-jre25-alpine-plus;10.3-alpine-plus;10-jre25-Temurin-alpine-plus;10-Temurin-alpine-plus;10-jre25-alpine-plus;10-alpine-plus;jre25-Temurin-alpine-plus;Temurin-alpine-plus;jre25-alpine-plus;alpine-plus
- Explicit moved aliases: 10-jre25-Temurin-alpine-plus;10-Temurin-alpine-plus;10-jre25-alpine-plus;10-alpine-plus;jre25-Temurin-alpine-plus;Temurin-alpine-plus;jre25-alpine-plus;alpine-plus
- Directories: `TomEE-10.2/jre25/Temurin/alpine/plus` → `TomEE-10.3/jre25/Temurin/alpine/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Temurin/alpine/webprofile

- Original tags: 10.2.0-jre25-Temurin-alpine-webprofile;10.2.0-Temurin-alpine-webprofile;10.2.0-jre25-alpine-webprofile;10.2.0-alpine-webprofile;10.1-jre25-Temurin-alpine-webprofile;10.1-Temurin-alpine-webprofile;10.1-jre25-alpine-webprofile;10.1-alpine-webprofile;10-jre25-Temurin-alpine-webprofile;10-Temurin-alpine-webprofile;10-jre25-alpine-webprofile;10-alpine-webprofile;jre25-Temurin-alpine-webprofile;Temurin-alpine-webprofile;jre25-alpine-webprofile;alpine-webprofile
- Retained tags: 10.2.0-jre25-Temurin-alpine-webprofile;10.2.0-Temurin-alpine-webprofile;10.2.0-jre25-alpine-webprofile;10.2.0-alpine-webprofile;10.1-jre25-Temurin-alpine-webprofile;10.1-Temurin-alpine-webprofile;10.1-jre25-alpine-webprofile;10.1-alpine-webprofile;10.2-jre25-Temurin-alpine-webprofile;10.2-Temurin-alpine-webprofile;10.2-jre25-alpine-webprofile;10.2-alpine-webprofile
- New tags: 10.3.0-jre25-Temurin-alpine-webprofile;10.3.0-Temurin-alpine-webprofile;10.3.0-jre25-alpine-webprofile;10.3.0-alpine-webprofile;10.3-jre25-Temurin-alpine-webprofile;10.3-Temurin-alpine-webprofile;10.3-jre25-alpine-webprofile;10.3-alpine-webprofile;10-jre25-Temurin-alpine-webprofile;10-Temurin-alpine-webprofile;10-jre25-alpine-webprofile;10-alpine-webprofile;jre25-Temurin-alpine-webprofile;Temurin-alpine-webprofile;jre25-alpine-webprofile;alpine-webprofile
- Explicit moved aliases: 10-jre25-Temurin-alpine-webprofile;10-Temurin-alpine-webprofile;10-jre25-alpine-webprofile;10-alpine-webprofile;jre25-Temurin-alpine-webprofile;Temurin-alpine-webprofile;jre25-alpine-webprofile;alpine-webprofile
- Directories: `TomEE-10.2/jre25/Temurin/alpine/webprofile` → `TomEE-10.3/jre25/Temurin/alpine/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Semeru/ubuntu/microprofile

- Original tags: 10.2.0-jre25-Semeru-ubuntu-microprofile;10.2.0-Semeru-ubuntu-microprofile;10.2.0-jre25-Semeru-microprofile;10.2.0-Semeru-microprofile;10.2.0-jre25-Semeru-ubuntu;10.2.0-Semeru-ubuntu;10.2.0-jre25-Semeru;10.2.0-Semeru;10.1-jre25-Semeru-ubuntu-microprofile;10.1-Semeru-ubuntu-microprofile;10.1-jre25-Semeru-microprofile;10.1-Semeru-microprofile;10.1-jre25-Semeru-ubuntu;10.1-Semeru-ubuntu;10.1-jre25-Semeru;10.1-Semeru;10-jre25-Semeru-ubuntu-microprofile;10-Semeru-ubuntu-microprofile;10-jre25-Semeru-microprofile;10-Semeru-microprofile;10-jre25-Semeru-ubuntu;10-Semeru-ubuntu;10-jre25-Semeru;10-Semeru;jre25-Semeru-ubuntu-microprofile;Semeru-ubuntu-microprofile;jre25-Semeru-microprofile;Semeru-microprofile;jre25-Semeru-ubuntu;Semeru-ubuntu;jre25-Semeru;Semeru
- Retained tags: 10.2.0-jre25-Semeru-ubuntu-microprofile;10.2.0-Semeru-ubuntu-microprofile;10.2.0-jre25-Semeru-microprofile;10.2.0-Semeru-microprofile;10.2.0-jre25-Semeru-ubuntu;10.2.0-Semeru-ubuntu;10.2.0-jre25-Semeru;10.2.0-Semeru;10.1-jre25-Semeru-ubuntu-microprofile;10.1-Semeru-ubuntu-microprofile;10.1-jre25-Semeru-microprofile;10.1-Semeru-microprofile;10.1-jre25-Semeru-ubuntu;10.1-Semeru-ubuntu;10.1-jre25-Semeru;10.1-Semeru;10.2-jre25-Semeru-ubuntu-microprofile;10.2-Semeru-ubuntu-microprofile;10.2-jre25-Semeru-microprofile;10.2-Semeru-microprofile;10.2-jre25-Semeru-ubuntu;10.2-Semeru-ubuntu;10.2-jre25-Semeru;10.2-Semeru
- New tags: 10.3.0-jre25-Semeru-ubuntu-microprofile;10.3.0-Semeru-ubuntu-microprofile;10.3.0-jre25-Semeru-microprofile;10.3.0-Semeru-microprofile;10.3.0-jre25-Semeru-ubuntu;10.3.0-Semeru-ubuntu;10.3.0-jre25-Semeru;10.3.0-Semeru;10.3-jre25-Semeru-ubuntu-microprofile;10.3-Semeru-ubuntu-microprofile;10.3-jre25-Semeru-microprofile;10.3-Semeru-microprofile;10.3-jre25-Semeru-ubuntu;10.3-Semeru-ubuntu;10.3-jre25-Semeru;10.3-Semeru;10-jre25-Semeru-ubuntu-microprofile;10-Semeru-ubuntu-microprofile;10-jre25-Semeru-microprofile;10-Semeru-microprofile;10-jre25-Semeru-ubuntu;10-Semeru-ubuntu;10-jre25-Semeru;10-Semeru;jre25-Semeru-ubuntu-microprofile;Semeru-ubuntu-microprofile;jre25-Semeru-microprofile;Semeru-microprofile;jre25-Semeru-ubuntu;Semeru-ubuntu;jre25-Semeru;Semeru
- Explicit moved aliases: 10-jre25-Semeru-ubuntu-microprofile;10-Semeru-ubuntu-microprofile;10-jre25-Semeru-microprofile;10-Semeru-microprofile;10-jre25-Semeru-ubuntu;10-Semeru-ubuntu;10-jre25-Semeru;10-Semeru;jre25-Semeru-ubuntu-microprofile;Semeru-ubuntu-microprofile;jre25-Semeru-microprofile;Semeru-microprofile;jre25-Semeru-ubuntu;Semeru-ubuntu;jre25-Semeru;Semeru
- Directories: `TomEE-10.2/jre25/Semeru/ubuntu/microprofile` → `TomEE-10.3/jre25/Semeru/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Semeru/ubuntu/plume

- Original tags: 10.2.0-jre25-Semeru-ubuntu-plume;10.2.0-Semeru-ubuntu-plume;10.2.0-jre25-Semeru-plume;10.2.0-Semeru-plume;10.1-jre25-Semeru-ubuntu-plume;10.1-Semeru-ubuntu-plume;10.1-jre25-Semeru-plume;10.1-Semeru-plume;10-jre25-Semeru-ubuntu-plume;10-Semeru-ubuntu-plume;10-jre25-Semeru-plume;10-Semeru-plume;jre25-Semeru-ubuntu-plume;Semeru-ubuntu-plume;jre25-Semeru-plume;Semeru-plume
- Retained tags: 10.2.0-jre25-Semeru-ubuntu-plume;10.2.0-Semeru-ubuntu-plume;10.2.0-jre25-Semeru-plume;10.2.0-Semeru-plume;10.1-jre25-Semeru-ubuntu-plume;10.1-Semeru-ubuntu-plume;10.1-jre25-Semeru-plume;10.1-Semeru-plume;10.2-jre25-Semeru-ubuntu-plume;10.2-Semeru-ubuntu-plume;10.2-jre25-Semeru-plume;10.2-Semeru-plume
- New tags: 10.3.0-jre25-Semeru-ubuntu-plume;10.3.0-Semeru-ubuntu-plume;10.3.0-jre25-Semeru-plume;10.3.0-Semeru-plume;10.3-jre25-Semeru-ubuntu-plume;10.3-Semeru-ubuntu-plume;10.3-jre25-Semeru-plume;10.3-Semeru-plume;10-jre25-Semeru-ubuntu-plume;10-Semeru-ubuntu-plume;10-jre25-Semeru-plume;10-Semeru-plume;jre25-Semeru-ubuntu-plume;Semeru-ubuntu-plume;jre25-Semeru-plume;Semeru-plume
- Explicit moved aliases: 10-jre25-Semeru-ubuntu-plume;10-Semeru-ubuntu-plume;10-jre25-Semeru-plume;10-Semeru-plume;jre25-Semeru-ubuntu-plume;Semeru-ubuntu-plume;jre25-Semeru-plume;Semeru-plume
- Directories: `TomEE-10.2/jre25/Semeru/ubuntu/plume` → `TomEE-10.3/jre25/Semeru/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Semeru/ubuntu/plus

- Original tags: 10.2.0-jre25-Semeru-ubuntu-plus;10.2.0-Semeru-ubuntu-plus;10.2.0-jre25-Semeru-plus;10.2.0-Semeru-plus;10.1-jre25-Semeru-ubuntu-plus;10.1-Semeru-ubuntu-plus;10.1-jre25-Semeru-plus;10.1-Semeru-plus;10-jre25-Semeru-ubuntu-plus;10-Semeru-ubuntu-plus;10-jre25-Semeru-plus;10-Semeru-plus;jre25-Semeru-ubuntu-plus;Semeru-ubuntu-plus;jre25-Semeru-plus;Semeru-plus
- Retained tags: 10.2.0-jre25-Semeru-ubuntu-plus;10.2.0-Semeru-ubuntu-plus;10.2.0-jre25-Semeru-plus;10.2.0-Semeru-plus;10.1-jre25-Semeru-ubuntu-plus;10.1-Semeru-ubuntu-plus;10.1-jre25-Semeru-plus;10.1-Semeru-plus;10.2-jre25-Semeru-ubuntu-plus;10.2-Semeru-ubuntu-plus;10.2-jre25-Semeru-plus;10.2-Semeru-plus
- New tags: 10.3.0-jre25-Semeru-ubuntu-plus;10.3.0-Semeru-ubuntu-plus;10.3.0-jre25-Semeru-plus;10.3.0-Semeru-plus;10.3-jre25-Semeru-ubuntu-plus;10.3-Semeru-ubuntu-plus;10.3-jre25-Semeru-plus;10.3-Semeru-plus;10-jre25-Semeru-ubuntu-plus;10-Semeru-ubuntu-plus;10-jre25-Semeru-plus;10-Semeru-plus;jre25-Semeru-ubuntu-plus;Semeru-ubuntu-plus;jre25-Semeru-plus;Semeru-plus
- Explicit moved aliases: 10-jre25-Semeru-ubuntu-plus;10-Semeru-ubuntu-plus;10-jre25-Semeru-plus;10-Semeru-plus;jre25-Semeru-ubuntu-plus;Semeru-ubuntu-plus;jre25-Semeru-plus;Semeru-plus
- Directories: `TomEE-10.2/jre25/Semeru/ubuntu/plus` → `TomEE-10.3/jre25/Semeru/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre25/Semeru/ubuntu/webprofile

- Original tags: 10.2.0-jre25-Semeru-ubuntu-webprofile;10.2.0-Semeru-ubuntu-webprofile;10.2.0-jre25-Semeru-webprofile;10.2.0-Semeru-webprofile;10.1-jre25-Semeru-ubuntu-webprofile;10.1-Semeru-ubuntu-webprofile;10.1-jre25-Semeru-webprofile;10.1-Semeru-webprofile;10-jre25-Semeru-ubuntu-webprofile;10-Semeru-ubuntu-webprofile;10-jre25-Semeru-webprofile;10-Semeru-webprofile;jre25-Semeru-ubuntu-webprofile;Semeru-ubuntu-webprofile;jre25-Semeru-webprofile;Semeru-webprofile
- Retained tags: 10.2.0-jre25-Semeru-ubuntu-webprofile;10.2.0-Semeru-ubuntu-webprofile;10.2.0-jre25-Semeru-webprofile;10.2.0-Semeru-webprofile;10.1-jre25-Semeru-ubuntu-webprofile;10.1-Semeru-ubuntu-webprofile;10.1-jre25-Semeru-webprofile;10.1-Semeru-webprofile;10.2-jre25-Semeru-ubuntu-webprofile;10.2-Semeru-ubuntu-webprofile;10.2-jre25-Semeru-webprofile;10.2-Semeru-webprofile
- New tags: 10.3.0-jre25-Semeru-ubuntu-webprofile;10.3.0-Semeru-ubuntu-webprofile;10.3.0-jre25-Semeru-webprofile;10.3.0-Semeru-webprofile;10.3-jre25-Semeru-ubuntu-webprofile;10.3-Semeru-ubuntu-webprofile;10.3-jre25-Semeru-webprofile;10.3-Semeru-webprofile;10-jre25-Semeru-ubuntu-webprofile;10-Semeru-ubuntu-webprofile;10-jre25-Semeru-webprofile;10-Semeru-webprofile;jre25-Semeru-ubuntu-webprofile;Semeru-ubuntu-webprofile;jre25-Semeru-webprofile;Semeru-webprofile
- Explicit moved aliases: 10-jre25-Semeru-ubuntu-webprofile;10-Semeru-ubuntu-webprofile;10-jre25-Semeru-webprofile;10-Semeru-webprofile;jre25-Semeru-ubuntu-webprofile;Semeru-ubuntu-webprofile;jre25-Semeru-webprofile;Semeru-webprofile
- Directories: `TomEE-10.2/jre25/Semeru/ubuntu/webprofile` → `TomEE-10.3/jre25/Semeru/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Temurin/ubuntu/microprofile

- Original tags: 10.2.0-jre21-Temurin-ubuntu-microprofile;10.2.0-jre21-ubuntu-microprofile;10.2.0-jre21-Temurin-microprofile;10.2.0-jre21-microprofile;10.2.0-jre21-Temurin-ubuntu;10.2.0-jre21-ubuntu;10.2.0-jre21-Temurin;10.2.0-jre21;10.1-jre21-Temurin-ubuntu-microprofile;10.1-jre21-ubuntu-microprofile;10.1-jre21-Temurin-microprofile;10.1-jre21-microprofile;10.1-jre21-Temurin-ubuntu;10.1-jre21-ubuntu;10.1-jre21-Temurin;10.1-jre21;10-jre21-Temurin-ubuntu-microprofile;10-jre21-ubuntu-microprofile;10-jre21-Temurin-microprofile;10-jre21-microprofile;10-jre21-Temurin-ubuntu;10-jre21-ubuntu;10-jre21-Temurin;10-jre21;jre21-Temurin-ubuntu-microprofile;jre21-ubuntu-microprofile;jre21-Temurin-microprofile;jre21-microprofile;jre21-Temurin-ubuntu;jre21-ubuntu;jre21-Temurin;jre21
- Retained tags: 10.2.0-jre21-Temurin-ubuntu-microprofile;10.2.0-jre21-ubuntu-microprofile;10.2.0-jre21-Temurin-microprofile;10.2.0-jre21-microprofile;10.2.0-jre21-Temurin-ubuntu;10.2.0-jre21-ubuntu;10.2.0-jre21-Temurin;10.2.0-jre21;10.1-jre21-Temurin-ubuntu-microprofile;10.1-jre21-ubuntu-microprofile;10.1-jre21-Temurin-microprofile;10.1-jre21-microprofile;10.1-jre21-Temurin-ubuntu;10.1-jre21-ubuntu;10.1-jre21-Temurin;10.1-jre21;10.2-jre21-Temurin-ubuntu-microprofile;10.2-jre21-ubuntu-microprofile;10.2-jre21-Temurin-microprofile;10.2-jre21-microprofile;10.2-jre21-Temurin-ubuntu;10.2-jre21-ubuntu;10.2-jre21-Temurin;10.2-jre21
- New tags: 10.3.0-jre21-Temurin-ubuntu-microprofile;10.3.0-jre21-ubuntu-microprofile;10.3.0-jre21-Temurin-microprofile;10.3.0-jre21-microprofile;10.3.0-jre21-Temurin-ubuntu;10.3.0-jre21-ubuntu;10.3.0-jre21-Temurin;10.3.0-jre21;10.3-jre21-Temurin-ubuntu-microprofile;10.3-jre21-ubuntu-microprofile;10.3-jre21-Temurin-microprofile;10.3-jre21-microprofile;10.3-jre21-Temurin-ubuntu;10.3-jre21-ubuntu;10.3-jre21-Temurin;10.3-jre21;10-jre21-Temurin-ubuntu-microprofile;10-jre21-ubuntu-microprofile;10-jre21-Temurin-microprofile;10-jre21-microprofile;10-jre21-Temurin-ubuntu;10-jre21-ubuntu;10-jre21-Temurin;10-jre21;jre21-Temurin-ubuntu-microprofile;jre21-ubuntu-microprofile;jre21-Temurin-microprofile;jre21-microprofile;jre21-Temurin-ubuntu;jre21-ubuntu;jre21-Temurin;jre21
- Explicit moved aliases: 10-jre21-Temurin-ubuntu-microprofile;10-jre21-ubuntu-microprofile;10-jre21-Temurin-microprofile;10-jre21-microprofile;10-jre21-Temurin-ubuntu;10-jre21-ubuntu;10-jre21-Temurin;10-jre21;jre21-Temurin-ubuntu-microprofile;jre21-ubuntu-microprofile;jre21-Temurin-microprofile;jre21-microprofile;jre21-Temurin-ubuntu;jre21-ubuntu;jre21-Temurin;jre21
- Directories: `TomEE-10.2/jre21/Temurin/ubuntu/microprofile` → `TomEE-10.3/jre21/Temurin/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Temurin/ubuntu/plume

- Original tags: 10.2.0-jre21-Temurin-ubuntu-plume;10.2.0-jre21-ubuntu-plume;10.2.0-jre21-Temurin-plume;10.2.0-jre21-plume;10.1-jre21-Temurin-ubuntu-plume;10.1-jre21-ubuntu-plume;10.1-jre21-Temurin-plume;10.1-jre21-plume;10-jre21-Temurin-ubuntu-plume;10-jre21-ubuntu-plume;10-jre21-Temurin-plume;10-jre21-plume;jre21-Temurin-ubuntu-plume;jre21-ubuntu-plume;jre21-Temurin-plume;jre21-plume
- Retained tags: 10.2.0-jre21-Temurin-ubuntu-plume;10.2.0-jre21-ubuntu-plume;10.2.0-jre21-Temurin-plume;10.2.0-jre21-plume;10.1-jre21-Temurin-ubuntu-plume;10.1-jre21-ubuntu-plume;10.1-jre21-Temurin-plume;10.1-jre21-plume;10.2-jre21-Temurin-ubuntu-plume;10.2-jre21-ubuntu-plume;10.2-jre21-Temurin-plume;10.2-jre21-plume
- New tags: 10.3.0-jre21-Temurin-ubuntu-plume;10.3.0-jre21-ubuntu-plume;10.3.0-jre21-Temurin-plume;10.3.0-jre21-plume;10.3-jre21-Temurin-ubuntu-plume;10.3-jre21-ubuntu-plume;10.3-jre21-Temurin-plume;10.3-jre21-plume;10-jre21-Temurin-ubuntu-plume;10-jre21-ubuntu-plume;10-jre21-Temurin-plume;10-jre21-plume;jre21-Temurin-ubuntu-plume;jre21-ubuntu-plume;jre21-Temurin-plume;jre21-plume
- Explicit moved aliases: 10-jre21-Temurin-ubuntu-plume;10-jre21-ubuntu-plume;10-jre21-Temurin-plume;10-jre21-plume;jre21-Temurin-ubuntu-plume;jre21-ubuntu-plume;jre21-Temurin-plume;jre21-plume
- Directories: `TomEE-10.2/jre21/Temurin/ubuntu/plume` → `TomEE-10.3/jre21/Temurin/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Temurin/ubuntu/plus

- Original tags: 10.2.0-jre21-Temurin-ubuntu-plus;10.2.0-jre21-ubuntu-plus;10.2.0-jre21-Temurin-plus;10.2.0-jre21-plus;10.1-jre21-Temurin-ubuntu-plus;10.1-jre21-ubuntu-plus;10.1-jre21-Temurin-plus;10.1-jre21-plus;10-jre21-Temurin-ubuntu-plus;10-jre21-ubuntu-plus;10-jre21-Temurin-plus;10-jre21-plus;jre21-Temurin-ubuntu-plus;jre21-ubuntu-plus;jre21-Temurin-plus;jre21-plus
- Retained tags: 10.2.0-jre21-Temurin-ubuntu-plus;10.2.0-jre21-ubuntu-plus;10.2.0-jre21-Temurin-plus;10.2.0-jre21-plus;10.1-jre21-Temurin-ubuntu-plus;10.1-jre21-ubuntu-plus;10.1-jre21-Temurin-plus;10.1-jre21-plus;10.2-jre21-Temurin-ubuntu-plus;10.2-jre21-ubuntu-plus;10.2-jre21-Temurin-plus;10.2-jre21-plus
- New tags: 10.3.0-jre21-Temurin-ubuntu-plus;10.3.0-jre21-ubuntu-plus;10.3.0-jre21-Temurin-plus;10.3.0-jre21-plus;10.3-jre21-Temurin-ubuntu-plus;10.3-jre21-ubuntu-plus;10.3-jre21-Temurin-plus;10.3-jre21-plus;10-jre21-Temurin-ubuntu-plus;10-jre21-ubuntu-plus;10-jre21-Temurin-plus;10-jre21-plus;jre21-Temurin-ubuntu-plus;jre21-ubuntu-plus;jre21-Temurin-plus;jre21-plus
- Explicit moved aliases: 10-jre21-Temurin-ubuntu-plus;10-jre21-ubuntu-plus;10-jre21-Temurin-plus;10-jre21-plus;jre21-Temurin-ubuntu-plus;jre21-ubuntu-plus;jre21-Temurin-plus;jre21-plus
- Directories: `TomEE-10.2/jre21/Temurin/ubuntu/plus` → `TomEE-10.3/jre21/Temurin/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Temurin/ubuntu/webprofile

- Original tags: 10.2.0-jre21-Temurin-ubuntu-webprofile;10.2.0-jre21-ubuntu-webprofile;10.2.0-jre21-Temurin-webprofile;10.2.0-jre21-webprofile;10.1-jre21-Temurin-ubuntu-webprofile;10.1-jre21-ubuntu-webprofile;10.1-jre21-Temurin-webprofile;10.1-jre21-webprofile;10-jre21-Temurin-ubuntu-webprofile;10-jre21-ubuntu-webprofile;10-jre21-Temurin-webprofile;10-jre21-webprofile;jre21-Temurin-ubuntu-webprofile;jre21-ubuntu-webprofile;jre21-Temurin-webprofile;jre21-webprofile
- Retained tags: 10.2.0-jre21-Temurin-ubuntu-webprofile;10.2.0-jre21-ubuntu-webprofile;10.2.0-jre21-Temurin-webprofile;10.2.0-jre21-webprofile;10.1-jre21-Temurin-ubuntu-webprofile;10.1-jre21-ubuntu-webprofile;10.1-jre21-Temurin-webprofile;10.1-jre21-webprofile;10.2-jre21-Temurin-ubuntu-webprofile;10.2-jre21-ubuntu-webprofile;10.2-jre21-Temurin-webprofile;10.2-jre21-webprofile
- New tags: 10.3.0-jre21-Temurin-ubuntu-webprofile;10.3.0-jre21-ubuntu-webprofile;10.3.0-jre21-Temurin-webprofile;10.3.0-jre21-webprofile;10.3-jre21-Temurin-ubuntu-webprofile;10.3-jre21-ubuntu-webprofile;10.3-jre21-Temurin-webprofile;10.3-jre21-webprofile;10-jre21-Temurin-ubuntu-webprofile;10-jre21-ubuntu-webprofile;10-jre21-Temurin-webprofile;10-jre21-webprofile;jre21-Temurin-ubuntu-webprofile;jre21-ubuntu-webprofile;jre21-Temurin-webprofile;jre21-webprofile
- Explicit moved aliases: 10-jre21-Temurin-ubuntu-webprofile;10-jre21-ubuntu-webprofile;10-jre21-Temurin-webprofile;10-jre21-webprofile;jre21-Temurin-ubuntu-webprofile;jre21-ubuntu-webprofile;jre21-Temurin-webprofile;jre21-webprofile
- Directories: `TomEE-10.2/jre21/Temurin/ubuntu/webprofile` → `TomEE-10.3/jre21/Temurin/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Temurin/alpine/microprofile

- Original tags: 10.2.0-jre21-Temurin-alpine-microprofile;10.2.0-jre21-alpine-microprofile;10.2.0-jre21-Temurin-alpine;10.2.0-jre21-alpine;10.1-jre21-Temurin-alpine-microprofile;10.1-jre21-alpine-microprofile;10.1-jre21-Temurin-alpine;10.1-jre21-alpine;10-jre21-Temurin-alpine-microprofile;10-jre21-alpine-microprofile;10-jre21-Temurin-alpine;10-jre21-alpine;jre21-Temurin-alpine-microprofile;jre21-alpine-microprofile;jre21-Temurin-alpine;jre21-alpine
- Retained tags: 10.2.0-jre21-Temurin-alpine-microprofile;10.2.0-jre21-alpine-microprofile;10.2.0-jre21-Temurin-alpine;10.2.0-jre21-alpine;10.1-jre21-Temurin-alpine-microprofile;10.1-jre21-alpine-microprofile;10.1-jre21-Temurin-alpine;10.1-jre21-alpine;10.2-jre21-Temurin-alpine-microprofile;10.2-jre21-alpine-microprofile;10.2-jre21-Temurin-alpine;10.2-jre21-alpine
- New tags: 10.3.0-jre21-Temurin-alpine-microprofile;10.3.0-jre21-alpine-microprofile;10.3.0-jre21-Temurin-alpine;10.3.0-jre21-alpine;10.3-jre21-Temurin-alpine-microprofile;10.3-jre21-alpine-microprofile;10.3-jre21-Temurin-alpine;10.3-jre21-alpine;10-jre21-Temurin-alpine-microprofile;10-jre21-alpine-microprofile;10-jre21-Temurin-alpine;10-jre21-alpine;jre21-Temurin-alpine-microprofile;jre21-alpine-microprofile;jre21-Temurin-alpine;jre21-alpine
- Explicit moved aliases: 10-jre21-Temurin-alpine-microprofile;10-jre21-alpine-microprofile;10-jre21-Temurin-alpine;10-jre21-alpine;jre21-Temurin-alpine-microprofile;jre21-alpine-microprofile;jre21-Temurin-alpine;jre21-alpine
- Directories: `TomEE-10.2/jre21/Temurin/alpine/microprofile` → `TomEE-10.3/jre21/Temurin/alpine/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Temurin/alpine/plume

- Original tags: 10.2.0-jre21-Temurin-alpine-plume;10.2.0-jre21-alpine-plume;10.1-jre21-Temurin-alpine-plume;10.1-jre21-alpine-plume;10-jre21-Temurin-alpine-plume;10-jre21-alpine-plume;jre21-Temurin-alpine-plume;jre21-alpine-plume
- Retained tags: 10.2.0-jre21-Temurin-alpine-plume;10.2.0-jre21-alpine-plume;10.1-jre21-Temurin-alpine-plume;10.1-jre21-alpine-plume;10.2-jre21-Temurin-alpine-plume;10.2-jre21-alpine-plume
- New tags: 10.3.0-jre21-Temurin-alpine-plume;10.3.0-jre21-alpine-plume;10.3-jre21-Temurin-alpine-plume;10.3-jre21-alpine-plume;10-jre21-Temurin-alpine-plume;10-jre21-alpine-plume;jre21-Temurin-alpine-plume;jre21-alpine-plume
- Explicit moved aliases: 10-jre21-Temurin-alpine-plume;10-jre21-alpine-plume;jre21-Temurin-alpine-plume;jre21-alpine-plume
- Directories: `TomEE-10.2/jre21/Temurin/alpine/plume` → `TomEE-10.3/jre21/Temurin/alpine/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Temurin/alpine/plus

- Original tags: 10.2.0-jre21-Temurin-alpine-plus;10.2.0-jre21-alpine-plus;10.1-jre21-Temurin-alpine-plus;10.1-jre21-alpine-plus;10-jre21-Temurin-alpine-plus;10-jre21-alpine-plus;jre21-Temurin-alpine-plus;jre21-alpine-plus
- Retained tags: 10.2.0-jre21-Temurin-alpine-plus;10.2.0-jre21-alpine-plus;10.1-jre21-Temurin-alpine-plus;10.1-jre21-alpine-plus;10.2-jre21-Temurin-alpine-plus;10.2-jre21-alpine-plus
- New tags: 10.3.0-jre21-Temurin-alpine-plus;10.3.0-jre21-alpine-plus;10.3-jre21-Temurin-alpine-plus;10.3-jre21-alpine-plus;10-jre21-Temurin-alpine-plus;10-jre21-alpine-plus;jre21-Temurin-alpine-plus;jre21-alpine-plus
- Explicit moved aliases: 10-jre21-Temurin-alpine-plus;10-jre21-alpine-plus;jre21-Temurin-alpine-plus;jre21-alpine-plus
- Directories: `TomEE-10.2/jre21/Temurin/alpine/plus` → `TomEE-10.3/jre21/Temurin/alpine/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Temurin/alpine/webprofile

- Original tags: 10.2.0-jre21-Temurin-alpine-webprofile;10.2.0-jre21-alpine-webprofile;10.1-jre21-Temurin-alpine-webprofile;10.1-jre21-alpine-webprofile;10-jre21-Temurin-alpine-webprofile;10-jre21-alpine-webprofile;jre21-Temurin-alpine-webprofile;jre21-alpine-webprofile
- Retained tags: 10.2.0-jre21-Temurin-alpine-webprofile;10.2.0-jre21-alpine-webprofile;10.1-jre21-Temurin-alpine-webprofile;10.1-jre21-alpine-webprofile;10.2-jre21-Temurin-alpine-webprofile;10.2-jre21-alpine-webprofile
- New tags: 10.3.0-jre21-Temurin-alpine-webprofile;10.3.0-jre21-alpine-webprofile;10.3-jre21-Temurin-alpine-webprofile;10.3-jre21-alpine-webprofile;10-jre21-Temurin-alpine-webprofile;10-jre21-alpine-webprofile;jre21-Temurin-alpine-webprofile;jre21-alpine-webprofile
- Explicit moved aliases: 10-jre21-Temurin-alpine-webprofile;10-jre21-alpine-webprofile;jre21-Temurin-alpine-webprofile;jre21-alpine-webprofile
- Directories: `TomEE-10.2/jre21/Temurin/alpine/webprofile` → `TomEE-10.3/jre21/Temurin/alpine/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Semeru/ubuntu/microprofile

- Original tags: 10.2.0-jre21-Semeru-ubuntu-microprofile;10.2.0-jre21-Semeru-microprofile;10.2.0-jre21-Semeru-ubuntu;10.2.0-jre21-Semeru;10.1-jre21-Semeru-ubuntu-microprofile;10.1-jre21-Semeru-microprofile;10.1-jre21-Semeru-ubuntu;10.1-jre21-Semeru;10-jre21-Semeru-ubuntu-microprofile;10-jre21-Semeru-microprofile;10-jre21-Semeru-ubuntu;10-jre21-Semeru;jre21-Semeru-ubuntu-microprofile;jre21-Semeru-microprofile;jre21-Semeru-ubuntu;jre21-Semeru
- Retained tags: 10.2.0-jre21-Semeru-ubuntu-microprofile;10.2.0-jre21-Semeru-microprofile;10.2.0-jre21-Semeru-ubuntu;10.2.0-jre21-Semeru;10.1-jre21-Semeru-ubuntu-microprofile;10.1-jre21-Semeru-microprofile;10.1-jre21-Semeru-ubuntu;10.1-jre21-Semeru;10.2-jre21-Semeru-ubuntu-microprofile;10.2-jre21-Semeru-microprofile;10.2-jre21-Semeru-ubuntu;10.2-jre21-Semeru
- New tags: 10.3.0-jre21-Semeru-ubuntu-microprofile;10.3.0-jre21-Semeru-microprofile;10.3.0-jre21-Semeru-ubuntu;10.3.0-jre21-Semeru;10.3-jre21-Semeru-ubuntu-microprofile;10.3-jre21-Semeru-microprofile;10.3-jre21-Semeru-ubuntu;10.3-jre21-Semeru;10-jre21-Semeru-ubuntu-microprofile;10-jre21-Semeru-microprofile;10-jre21-Semeru-ubuntu;10-jre21-Semeru;jre21-Semeru-ubuntu-microprofile;jre21-Semeru-microprofile;jre21-Semeru-ubuntu;jre21-Semeru
- Explicit moved aliases: 10-jre21-Semeru-ubuntu-microprofile;10-jre21-Semeru-microprofile;10-jre21-Semeru-ubuntu;10-jre21-Semeru;jre21-Semeru-ubuntu-microprofile;jre21-Semeru-microprofile;jre21-Semeru-ubuntu;jre21-Semeru
- Directories: `TomEE-10.2/jre21/Semeru/ubuntu/microprofile` → `TomEE-10.3/jre21/Semeru/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Semeru/ubuntu/plume

- Original tags: 10.2.0-jre21-Semeru-ubuntu-plume;10.2.0-jre21-Semeru-plume;10.1-jre21-Semeru-ubuntu-plume;10.1-jre21-Semeru-plume;10-jre21-Semeru-ubuntu-plume;10-jre21-Semeru-plume;jre21-Semeru-ubuntu-plume;jre21-Semeru-plume
- Retained tags: 10.2.0-jre21-Semeru-ubuntu-plume;10.2.0-jre21-Semeru-plume;10.1-jre21-Semeru-ubuntu-plume;10.1-jre21-Semeru-plume;10.2-jre21-Semeru-ubuntu-plume;10.2-jre21-Semeru-plume
- New tags: 10.3.0-jre21-Semeru-ubuntu-plume;10.3.0-jre21-Semeru-plume;10.3-jre21-Semeru-ubuntu-plume;10.3-jre21-Semeru-plume;10-jre21-Semeru-ubuntu-plume;10-jre21-Semeru-plume;jre21-Semeru-ubuntu-plume;jre21-Semeru-plume
- Explicit moved aliases: 10-jre21-Semeru-ubuntu-plume;10-jre21-Semeru-plume;jre21-Semeru-ubuntu-plume;jre21-Semeru-plume
- Directories: `TomEE-10.2/jre21/Semeru/ubuntu/plume` → `TomEE-10.3/jre21/Semeru/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Semeru/ubuntu/plus

- Original tags: 10.2.0-jre21-Semeru-ubuntu-plus;10.2.0-jre21-Semeru-plus;10.1-jre21-Semeru-ubuntu-plus;10.1-jre21-Semeru-plus;10-jre21-Semeru-ubuntu-plus;10-jre21-Semeru-plus;jre21-Semeru-ubuntu-plus;jre21-Semeru-plus
- Retained tags: 10.2.0-jre21-Semeru-ubuntu-plus;10.2.0-jre21-Semeru-plus;10.1-jre21-Semeru-ubuntu-plus;10.1-jre21-Semeru-plus;10.2-jre21-Semeru-ubuntu-plus;10.2-jre21-Semeru-plus
- New tags: 10.3.0-jre21-Semeru-ubuntu-plus;10.3.0-jre21-Semeru-plus;10.3-jre21-Semeru-ubuntu-plus;10.3-jre21-Semeru-plus;10-jre21-Semeru-ubuntu-plus;10-jre21-Semeru-plus;jre21-Semeru-ubuntu-plus;jre21-Semeru-plus
- Explicit moved aliases: 10-jre21-Semeru-ubuntu-plus;10-jre21-Semeru-plus;jre21-Semeru-ubuntu-plus;jre21-Semeru-plus
- Directories: `TomEE-10.2/jre21/Semeru/ubuntu/plus` → `TomEE-10.3/jre21/Semeru/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre21/Semeru/ubuntu/webprofile

- Original tags: 10.2.0-jre21-Semeru-ubuntu-webprofile;10.2.0-jre21-Semeru-webprofile;10.1-jre21-Semeru-ubuntu-webprofile;10.1-jre21-Semeru-webprofile;10-jre21-Semeru-ubuntu-webprofile;10-jre21-Semeru-webprofile;jre21-Semeru-ubuntu-webprofile;jre21-Semeru-webprofile
- Retained tags: 10.2.0-jre21-Semeru-ubuntu-webprofile;10.2.0-jre21-Semeru-webprofile;10.1-jre21-Semeru-ubuntu-webprofile;10.1-jre21-Semeru-webprofile;10.2-jre21-Semeru-ubuntu-webprofile;10.2-jre21-Semeru-webprofile
- New tags: 10.3.0-jre21-Semeru-ubuntu-webprofile;10.3.0-jre21-Semeru-webprofile;10.3-jre21-Semeru-ubuntu-webprofile;10.3-jre21-Semeru-webprofile;10-jre21-Semeru-ubuntu-webprofile;10-jre21-Semeru-webprofile;jre21-Semeru-ubuntu-webprofile;jre21-Semeru-webprofile
- Explicit moved aliases: 10-jre21-Semeru-ubuntu-webprofile;10-jre21-Semeru-webprofile;jre21-Semeru-ubuntu-webprofile;jre21-Semeru-webprofile
- Directories: `TomEE-10.2/jre21/Semeru/ubuntu/webprofile` → `TomEE-10.3/jre21/Semeru/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre17/Temurin/ubuntu/microprofile

- Original tags: 10.2.0-jre17-Temurin-ubuntu-microprofile;10.2.0-jre17-ubuntu-microprofile;10.2.0-jre17-Temurin-microprofile;10.2.0-jre17-microprofile;10.2.0-jre17-Temurin-ubuntu;10.2.0-jre17-ubuntu;10.2.0-jre17-Temurin;10.2.0-jre17;10.1-jre17-Temurin-ubuntu-microprofile;10.1-jre17-ubuntu-microprofile;10.1-jre17-Temurin-microprofile;10.1-jre17-microprofile;10.1-jre17-Temurin-ubuntu;10.1-jre17-ubuntu;10.1-jre17-Temurin;10.1-jre17;10-jre17-Temurin-ubuntu-microprofile;10-jre17-ubuntu-microprofile;10-jre17-Temurin-microprofile;10-jre17-microprofile;10-jre17-Temurin-ubuntu;10-jre17-ubuntu;10-jre17-Temurin;10-jre17;jre17-Temurin-ubuntu-microprofile;jre17-ubuntu-microprofile;jre17-Temurin-microprofile;jre17-microprofile;jre17-Temurin-ubuntu;jre17-ubuntu;jre17-Temurin;jre17
- Retained tags: 10.2.0-jre17-Temurin-ubuntu-microprofile;10.2.0-jre17-ubuntu-microprofile;10.2.0-jre17-Temurin-microprofile;10.2.0-jre17-microprofile;10.2.0-jre17-Temurin-ubuntu;10.2.0-jre17-ubuntu;10.2.0-jre17-Temurin;10.2.0-jre17;10.1-jre17-Temurin-ubuntu-microprofile;10.1-jre17-ubuntu-microprofile;10.1-jre17-Temurin-microprofile;10.1-jre17-microprofile;10.1-jre17-Temurin-ubuntu;10.1-jre17-ubuntu;10.1-jre17-Temurin;10.1-jre17;10.2-jre17-Temurin-ubuntu-microprofile;10.2-jre17-ubuntu-microprofile;10.2-jre17-Temurin-microprofile;10.2-jre17-microprofile;10.2-jre17-Temurin-ubuntu;10.2-jre17-ubuntu;10.2-jre17-Temurin;10.2-jre17
- New tags: 10.3.0-jre17-Temurin-ubuntu-microprofile;10.3.0-jre17-ubuntu-microprofile;10.3.0-jre17-Temurin-microprofile;10.3.0-jre17-microprofile;10.3.0-jre17-Temurin-ubuntu;10.3.0-jre17-ubuntu;10.3.0-jre17-Temurin;10.3.0-jre17;10.3-jre17-Temurin-ubuntu-microprofile;10.3-jre17-ubuntu-microprofile;10.3-jre17-Temurin-microprofile;10.3-jre17-microprofile;10.3-jre17-Temurin-ubuntu;10.3-jre17-ubuntu;10.3-jre17-Temurin;10.3-jre17;10-jre17-Temurin-ubuntu-microprofile;10-jre17-ubuntu-microprofile;10-jre17-Temurin-microprofile;10-jre17-microprofile;10-jre17-Temurin-ubuntu;10-jre17-ubuntu;10-jre17-Temurin;10-jre17;jre17-Temurin-ubuntu-microprofile;jre17-ubuntu-microprofile;jre17-Temurin-microprofile;jre17-microprofile;jre17-Temurin-ubuntu;jre17-ubuntu;jre17-Temurin;jre17
- Explicit moved aliases: 10-jre17-Temurin-ubuntu-microprofile;10-jre17-ubuntu-microprofile;10-jre17-Temurin-microprofile;10-jre17-microprofile;10-jre17-Temurin-ubuntu;10-jre17-ubuntu;10-jre17-Temurin;10-jre17;jre17-Temurin-ubuntu-microprofile;jre17-ubuntu-microprofile;jre17-Temurin-microprofile;jre17-microprofile;jre17-Temurin-ubuntu;jre17-ubuntu;jre17-Temurin;jre17
- Directories: `TomEE-10.2/jre17/Temurin/ubuntu/microprofile` → `TomEE-10.3/jre17/Temurin/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre17/Temurin/ubuntu/plume

- Original tags: 10.2.0-jre17-Temurin-ubuntu-plume;10.2.0-jre17-ubuntu-plume;10.2.0-jre17-Temurin-plume;10.2.0-jre17-plume;10.1-jre17-Temurin-ubuntu-plume;10.1-jre17-ubuntu-plume;10.1-jre17-Temurin-plume;10.1-jre17-plume;10-jre17-Temurin-ubuntu-plume;10-jre17-ubuntu-plume;10-jre17-Temurin-plume;10-jre17-plume;jre17-Temurin-ubuntu-plume;jre17-ubuntu-plume;jre17-Temurin-plume;jre17-plume
- Retained tags: 10.2.0-jre17-Temurin-ubuntu-plume;10.2.0-jre17-ubuntu-plume;10.2.0-jre17-Temurin-plume;10.2.0-jre17-plume;10.1-jre17-Temurin-ubuntu-plume;10.1-jre17-ubuntu-plume;10.1-jre17-Temurin-plume;10.1-jre17-plume;10.2-jre17-Temurin-ubuntu-plume;10.2-jre17-ubuntu-plume;10.2-jre17-Temurin-plume;10.2-jre17-plume
- New tags: 10.3.0-jre17-Temurin-ubuntu-plume;10.3.0-jre17-ubuntu-plume;10.3.0-jre17-Temurin-plume;10.3.0-jre17-plume;10.3-jre17-Temurin-ubuntu-plume;10.3-jre17-ubuntu-plume;10.3-jre17-Temurin-plume;10.3-jre17-plume;10-jre17-Temurin-ubuntu-plume;10-jre17-ubuntu-plume;10-jre17-Temurin-plume;10-jre17-plume;jre17-Temurin-ubuntu-plume;jre17-ubuntu-plume;jre17-Temurin-plume;jre17-plume
- Explicit moved aliases: 10-jre17-Temurin-ubuntu-plume;10-jre17-ubuntu-plume;10-jre17-Temurin-plume;10-jre17-plume;jre17-Temurin-ubuntu-plume;jre17-ubuntu-plume;jre17-Temurin-plume;jre17-plume
- Directories: `TomEE-10.2/jre17/Temurin/ubuntu/plume` → `TomEE-10.3/jre17/Temurin/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre17/Temurin/ubuntu/plus

- Original tags: 10.2.0-jre17-Temurin-ubuntu-plus;10.2.0-jre17-ubuntu-plus;10.2.0-jre17-Temurin-plus;10.2.0-jre17-plus;10.1-jre17-Temurin-ubuntu-plus;10.1-jre17-ubuntu-plus;10.1-jre17-Temurin-plus;10.1-jre17-plus;10-jre17-Temurin-ubuntu-plus;10-jre17-ubuntu-plus;10-jre17-Temurin-plus;10-jre17-plus;jre17-Temurin-ubuntu-plus;jre17-ubuntu-plus;jre17-Temurin-plus;jre17-plus
- Retained tags: 10.2.0-jre17-Temurin-ubuntu-plus;10.2.0-jre17-ubuntu-plus;10.2.0-jre17-Temurin-plus;10.2.0-jre17-plus;10.1-jre17-Temurin-ubuntu-plus;10.1-jre17-ubuntu-plus;10.1-jre17-Temurin-plus;10.1-jre17-plus;10.2-jre17-Temurin-ubuntu-plus;10.2-jre17-ubuntu-plus;10.2-jre17-Temurin-plus;10.2-jre17-plus
- New tags: 10.3.0-jre17-Temurin-ubuntu-plus;10.3.0-jre17-ubuntu-plus;10.3.0-jre17-Temurin-plus;10.3.0-jre17-plus;10.3-jre17-Temurin-ubuntu-plus;10.3-jre17-ubuntu-plus;10.3-jre17-Temurin-plus;10.3-jre17-plus;10-jre17-Temurin-ubuntu-plus;10-jre17-ubuntu-plus;10-jre17-Temurin-plus;10-jre17-plus;jre17-Temurin-ubuntu-plus;jre17-ubuntu-plus;jre17-Temurin-plus;jre17-plus
- Explicit moved aliases: 10-jre17-Temurin-ubuntu-plus;10-jre17-ubuntu-plus;10-jre17-Temurin-plus;10-jre17-plus;jre17-Temurin-ubuntu-plus;jre17-ubuntu-plus;jre17-Temurin-plus;jre17-plus
- Directories: `TomEE-10.2/jre17/Temurin/ubuntu/plus` → `TomEE-10.3/jre17/Temurin/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre17/Temurin/ubuntu/webprofile

- Original tags: 10.2.0-jre17-Temurin-ubuntu-webprofile;10.2.0-jre17-ubuntu-webprofile;10.2.0-jre17-Temurin-webprofile;10.2.0-jre17-webprofile;10.1-jre17-Temurin-ubuntu-webprofile;10.1-jre17-ubuntu-webprofile;10.1-jre17-Temurin-webprofile;10.1-jre17-webprofile;10-jre17-Temurin-ubuntu-webprofile;10-jre17-ubuntu-webprofile;10-jre17-Temurin-webprofile;10-jre17-webprofile;jre17-Temurin-ubuntu-webprofile;jre17-ubuntu-webprofile;jre17-Temurin-webprofile;jre17-webprofile
- Retained tags: 10.2.0-jre17-Temurin-ubuntu-webprofile;10.2.0-jre17-ubuntu-webprofile;10.2.0-jre17-Temurin-webprofile;10.2.0-jre17-webprofile;10.1-jre17-Temurin-ubuntu-webprofile;10.1-jre17-ubuntu-webprofile;10.1-jre17-Temurin-webprofile;10.1-jre17-webprofile;10.2-jre17-Temurin-ubuntu-webprofile;10.2-jre17-ubuntu-webprofile;10.2-jre17-Temurin-webprofile;10.2-jre17-webprofile
- New tags: 10.3.0-jre17-Temurin-ubuntu-webprofile;10.3.0-jre17-ubuntu-webprofile;10.3.0-jre17-Temurin-webprofile;10.3.0-jre17-webprofile;10.3-jre17-Temurin-ubuntu-webprofile;10.3-jre17-ubuntu-webprofile;10.3-jre17-Temurin-webprofile;10.3-jre17-webprofile;10-jre17-Temurin-ubuntu-webprofile;10-jre17-ubuntu-webprofile;10-jre17-Temurin-webprofile;10-jre17-webprofile;jre17-Temurin-ubuntu-webprofile;jre17-ubuntu-webprofile;jre17-Temurin-webprofile;jre17-webprofile
- Explicit moved aliases: 10-jre17-Temurin-ubuntu-webprofile;10-jre17-ubuntu-webprofile;10-jre17-Temurin-webprofile;10-jre17-webprofile;jre17-Temurin-ubuntu-webprofile;jre17-ubuntu-webprofile;jre17-Temurin-webprofile;jre17-webprofile
- Directories: `TomEE-10.2/jre17/Temurin/ubuntu/webprofile` → `TomEE-10.3/jre17/Temurin/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre17/Temurin/alpine/microprofile

- Original tags: 10.2.0-jre17-Temurin-alpine-microprofile;10.2.0-jre17-alpine-microprofile;10.2.0-jre17-Temurin-alpine;10.2.0-jre17-alpine;10.1-jre17-Temurin-alpine-microprofile;10.1-jre17-alpine-microprofile;10.1-jre17-Temurin-alpine;10.1-jre17-alpine;10-jre17-Temurin-alpine-microprofile;10-jre17-alpine-microprofile;10-jre17-Temurin-alpine;10-jre17-alpine;jre17-Temurin-alpine-microprofile;jre17-alpine-microprofile;jre17-Temurin-alpine;jre17-alpine
- Retained tags: 10.2.0-jre17-Temurin-alpine-microprofile;10.2.0-jre17-alpine-microprofile;10.2.0-jre17-Temurin-alpine;10.2.0-jre17-alpine;10.1-jre17-Temurin-alpine-microprofile;10.1-jre17-alpine-microprofile;10.1-jre17-Temurin-alpine;10.1-jre17-alpine;10.2-jre17-Temurin-alpine-microprofile;10.2-jre17-alpine-microprofile;10.2-jre17-Temurin-alpine;10.2-jre17-alpine
- New tags: 10.3.0-jre17-Temurin-alpine-microprofile;10.3.0-jre17-alpine-microprofile;10.3.0-jre17-Temurin-alpine;10.3.0-jre17-alpine;10.3-jre17-Temurin-alpine-microprofile;10.3-jre17-alpine-microprofile;10.3-jre17-Temurin-alpine;10.3-jre17-alpine;10-jre17-Temurin-alpine-microprofile;10-jre17-alpine-microprofile;10-jre17-Temurin-alpine;10-jre17-alpine;jre17-Temurin-alpine-microprofile;jre17-alpine-microprofile;jre17-Temurin-alpine;jre17-alpine
- Explicit moved aliases: 10-jre17-Temurin-alpine-microprofile;10-jre17-alpine-microprofile;10-jre17-Temurin-alpine;10-jre17-alpine;jre17-Temurin-alpine-microprofile;jre17-alpine-microprofile;jre17-Temurin-alpine;jre17-alpine
- Directories: `TomEE-10.2/jre17/Temurin/alpine/microprofile` → `TomEE-10.3/jre17/Temurin/alpine/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64` → `amd64`

### 10_2_to_10_3 — TomEE-10.2/jre17/Temurin/alpine/plume

- Original tags: 10.2.0-jre17-Temurin-alpine-plume;10.2.0-jre17-alpine-plume;10.1-jre17-Temurin-alpine-plume;10.1-jre17-alpine-plume;10-jre17-Temurin-alpine-plume;10-jre17-alpine-plume;jre17-Temurin-alpine-plume;jre17-alpine-plume
- Retained tags: 10.2.0-jre17-Temurin-alpine-plume;10.2.0-jre17-alpine-plume;10.1-jre17-Temurin-alpine-plume;10.1-jre17-alpine-plume;10.2-jre17-Temurin-alpine-plume;10.2-jre17-alpine-plume
- New tags: 10.3.0-jre17-Temurin-alpine-plume;10.3.0-jre17-alpine-plume;10.3-jre17-Temurin-alpine-plume;10.3-jre17-alpine-plume;10-jre17-Temurin-alpine-plume;10-jre17-alpine-plume;jre17-Temurin-alpine-plume;jre17-alpine-plume
- Explicit moved aliases: 10-jre17-Temurin-alpine-plume;10-jre17-alpine-plume;jre17-Temurin-alpine-plume;jre17-alpine-plume
- Directories: `TomEE-10.2/jre17/Temurin/alpine/plume` → `TomEE-10.3/jre17/Temurin/alpine/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64` → `amd64`

### 10_2_to_10_3 — TomEE-10.2/jre17/Temurin/alpine/plus

- Original tags: 10.2.0-jre17-Temurin-alpine-plus;10.2.0-jre17-alpine-plus;10.1-jre17-Temurin-alpine-plus;10.1-jre17-alpine-plus;10-jre17-Temurin-alpine-plus;10-jre17-alpine-plus;jre17-Temurin-alpine-plus;jre17-alpine-plus
- Retained tags: 10.2.0-jre17-Temurin-alpine-plus;10.2.0-jre17-alpine-plus;10.1-jre17-Temurin-alpine-plus;10.1-jre17-alpine-plus;10.2-jre17-Temurin-alpine-plus;10.2-jre17-alpine-plus
- New tags: 10.3.0-jre17-Temurin-alpine-plus;10.3.0-jre17-alpine-plus;10.3-jre17-Temurin-alpine-plus;10.3-jre17-alpine-plus;10-jre17-Temurin-alpine-plus;10-jre17-alpine-plus;jre17-Temurin-alpine-plus;jre17-alpine-plus
- Explicit moved aliases: 10-jre17-Temurin-alpine-plus;10-jre17-alpine-plus;jre17-Temurin-alpine-plus;jre17-alpine-plus
- Directories: `TomEE-10.2/jre17/Temurin/alpine/plus` → `TomEE-10.3/jre17/Temurin/alpine/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64` → `amd64`

### 10_2_to_10_3 — TomEE-10.2/jre17/Temurin/alpine/webprofile

- Original tags: 10.2.0-jre17-Temurin-alpine-webprofile;10.2.0-jre17-alpine-webprofile;10.1-jre17-Temurin-alpine-webprofile;10.1-jre17-alpine-webprofile;10-jre17-Temurin-alpine-webprofile;10-jre17-alpine-webprofile;jre17-Temurin-alpine-webprofile;jre17-alpine-webprofile
- Retained tags: 10.2.0-jre17-Temurin-alpine-webprofile;10.2.0-jre17-alpine-webprofile;10.1-jre17-Temurin-alpine-webprofile;10.1-jre17-alpine-webprofile;10.2-jre17-Temurin-alpine-webprofile;10.2-jre17-alpine-webprofile
- New tags: 10.3.0-jre17-Temurin-alpine-webprofile;10.3.0-jre17-alpine-webprofile;10.3-jre17-Temurin-alpine-webprofile;10.3-jre17-alpine-webprofile;10-jre17-Temurin-alpine-webprofile;10-jre17-alpine-webprofile;jre17-Temurin-alpine-webprofile;jre17-alpine-webprofile
- Explicit moved aliases: 10-jre17-Temurin-alpine-webprofile;10-jre17-alpine-webprofile;jre17-Temurin-alpine-webprofile;jre17-alpine-webprofile
- Directories: `TomEE-10.2/jre17/Temurin/alpine/webprofile` → `TomEE-10.3/jre17/Temurin/alpine/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64` → `amd64`

### 10_2_to_10_3 — TomEE-10.2/jre17/Semeru/ubuntu/microprofile

- Original tags: 10.2.0-jre17-Semeru-ubuntu-microprofile;10.2.0-jre17-Semeru-microprofile;10.2.0-jre17-Semeru-ubuntu;10.2.0-jre17-Semeru;10.1-jre17-Semeru-ubuntu-microprofile;10.1-jre17-Semeru-microprofile;10.1-jre17-Semeru-ubuntu;10.1-jre17-Semeru;10-jre17-Semeru-ubuntu-microprofile;10-jre17-Semeru-microprofile;10-jre17-Semeru-ubuntu;10-jre17-Semeru;jre17-Semeru-ubuntu-microprofile;jre17-Semeru-microprofile;jre17-Semeru-ubuntu;jre17-Semeru
- Retained tags: 10.2.0-jre17-Semeru-ubuntu-microprofile;10.2.0-jre17-Semeru-microprofile;10.2.0-jre17-Semeru-ubuntu;10.2.0-jre17-Semeru;10.1-jre17-Semeru-ubuntu-microprofile;10.1-jre17-Semeru-microprofile;10.1-jre17-Semeru-ubuntu;10.1-jre17-Semeru;10.2-jre17-Semeru-ubuntu-microprofile;10.2-jre17-Semeru-microprofile;10.2-jre17-Semeru-ubuntu;10.2-jre17-Semeru
- New tags: 10.3.0-jre17-Semeru-ubuntu-microprofile;10.3.0-jre17-Semeru-microprofile;10.3.0-jre17-Semeru-ubuntu;10.3.0-jre17-Semeru;10.3-jre17-Semeru-ubuntu-microprofile;10.3-jre17-Semeru-microprofile;10.3-jre17-Semeru-ubuntu;10.3-jre17-Semeru;10-jre17-Semeru-ubuntu-microprofile;10-jre17-Semeru-microprofile;10-jre17-Semeru-ubuntu;10-jre17-Semeru;jre17-Semeru-ubuntu-microprofile;jre17-Semeru-microprofile;jre17-Semeru-ubuntu;jre17-Semeru
- Explicit moved aliases: 10-jre17-Semeru-ubuntu-microprofile;10-jre17-Semeru-microprofile;10-jre17-Semeru-ubuntu;10-jre17-Semeru;jre17-Semeru-ubuntu-microprofile;jre17-Semeru-microprofile;jre17-Semeru-ubuntu;jre17-Semeru
- Directories: `TomEE-10.2/jre17/Semeru/ubuntu/microprofile` → `TomEE-10.3/jre17/Semeru/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre17/Semeru/ubuntu/plume

- Original tags: 10.2.0-jre17-Semeru-ubuntu-plume;10.2.0-jre17-Semeru-plume;10.1-jre17-Semeru-ubuntu-plume;10.1-jre17-Semeru-plume;10-jre17-Semeru-ubuntu-plume;10-jre17-Semeru-plume;jre17-Semeru-ubuntu-plume;jre17-Semeru-plume
- Retained tags: 10.2.0-jre17-Semeru-ubuntu-plume;10.2.0-jre17-Semeru-plume;10.1-jre17-Semeru-ubuntu-plume;10.1-jre17-Semeru-plume;10.2-jre17-Semeru-ubuntu-plume;10.2-jre17-Semeru-plume
- New tags: 10.3.0-jre17-Semeru-ubuntu-plume;10.3.0-jre17-Semeru-plume;10.3-jre17-Semeru-ubuntu-plume;10.3-jre17-Semeru-plume;10-jre17-Semeru-ubuntu-plume;10-jre17-Semeru-plume;jre17-Semeru-ubuntu-plume;jre17-Semeru-plume
- Explicit moved aliases: 10-jre17-Semeru-ubuntu-plume;10-jre17-Semeru-plume;jre17-Semeru-ubuntu-plume;jre17-Semeru-plume
- Directories: `TomEE-10.2/jre17/Semeru/ubuntu/plume` → `TomEE-10.3/jre17/Semeru/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre17/Semeru/ubuntu/plus

- Original tags: 10.2.0-jre17-Semeru-ubuntu-plus;10.2.0-jre17-Semeru-plus;10.1-jre17-Semeru-ubuntu-plus;10.1-jre17-Semeru-plus;10-jre17-Semeru-ubuntu-plus;10-jre17-Semeru-plus;jre17-Semeru-ubuntu-plus;jre17-Semeru-plus
- Retained tags: 10.2.0-jre17-Semeru-ubuntu-plus;10.2.0-jre17-Semeru-plus;10.1-jre17-Semeru-ubuntu-plus;10.1-jre17-Semeru-plus;10.2-jre17-Semeru-ubuntu-plus;10.2-jre17-Semeru-plus
- New tags: 10.3.0-jre17-Semeru-ubuntu-plus;10.3.0-jre17-Semeru-plus;10.3-jre17-Semeru-ubuntu-plus;10.3-jre17-Semeru-plus;10-jre17-Semeru-ubuntu-plus;10-jre17-Semeru-plus;jre17-Semeru-ubuntu-plus;jre17-Semeru-plus
- Explicit moved aliases: 10-jre17-Semeru-ubuntu-plus;10-jre17-Semeru-plus;jre17-Semeru-ubuntu-plus;jre17-Semeru-plus
- Directories: `TomEE-10.2/jre17/Semeru/ubuntu/plus` → `TomEE-10.3/jre17/Semeru/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 10_2_to_10_3 — TomEE-10.2/jre17/Semeru/ubuntu/webprofile

- Original tags: 10.2.0-jre17-Semeru-ubuntu-webprofile;10.2.0-jre17-Semeru-webprofile;10.1-jre17-Semeru-ubuntu-webprofile;10.1-jre17-Semeru-webprofile;10-jre17-Semeru-ubuntu-webprofile;10-jre17-Semeru-webprofile;jre17-Semeru-ubuntu-webprofile;jre17-Semeru-webprofile
- Retained tags: 10.2.0-jre17-Semeru-ubuntu-webprofile;10.2.0-jre17-Semeru-webprofile;10.1-jre17-Semeru-ubuntu-webprofile;10.1-jre17-Semeru-webprofile;10.2-jre17-Semeru-ubuntu-webprofile;10.2-jre17-Semeru-webprofile
- New tags: 10.3.0-jre17-Semeru-ubuntu-webprofile;10.3.0-jre17-Semeru-webprofile;10.3-jre17-Semeru-ubuntu-webprofile;10.3-jre17-Semeru-webprofile;10-jre17-Semeru-ubuntu-webprofile;10-jre17-Semeru-webprofile;jre17-Semeru-ubuntu-webprofile;jre17-Semeru-webprofile
- Explicit moved aliases: 10-jre17-Semeru-ubuntu-webprofile;10-jre17-Semeru-webprofile;jre17-Semeru-ubuntu-webprofile;jre17-Semeru-webprofile
- Directories: `TomEE-10.2/jre17/Semeru/ubuntu/webprofile` → `TomEE-10.3/jre17/Semeru/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Temurin/ubuntu/microprofile

- Original tags: 11.0.0-M1-jre25-Temurin-ubuntu-microprofile;11.0.0-M1-Temurin-ubuntu-microprofile;11.0.0-M1-jre25-ubuntu-microprofile;11.0.0-M1-ubuntu-microprofile;11.0.0-M1-jre25-Temurin-microprofile;11.0.0-M1-Temurin-microprofile;11.0.0-M1-jre25-microprofile;11.0.0-M1-microprofile;11.0.0-M1-jre25-Temurin-ubuntu;11.0.0-M1-Temurin-ubuntu;11.0.0-M1-jre25-ubuntu;11.0.0-M1-ubuntu;11.0.0-M1-jre25-Temurin;11.0.0-M1-Temurin;11.0.0-M1-jre25;11.0.0-M1;11.0-jre25-Temurin-ubuntu-microprofile;11.0-Temurin-ubuntu-microprofile;11.0-jre25-ubuntu-microprofile;11.0-ubuntu-microprofile;11.0-jre25-Temurin-microprofile;11.0-Temurin-microprofile;11.0-jre25-microprofile;11.0-microprofile;11.0-jre25-Temurin-ubuntu;11.0-Temurin-ubuntu;11.0-jre25-ubuntu;11.0-ubuntu;11.0-jre25-Temurin;11.0-Temurin;11.0-jre25;11.0;11-jre25-Temurin-ubuntu-microprofile;11-Temurin-ubuntu-microprofile;11-jre25-ubuntu-microprofile;11-ubuntu-microprofile;11-jre25-Temurin-microprofile;11-Temurin-microprofile;11-jre25-microprofile;11-microprofile;11-jre25-Temurin-ubuntu;11-Temurin-ubuntu;11-jre25-ubuntu;11-ubuntu;11-jre25-Temurin;11-Temurin;11-jre25;11
- Retained tags: 11.0.0-M1-jre25-Temurin-ubuntu-microprofile;11.0.0-M1-Temurin-ubuntu-microprofile;11.0.0-M1-jre25-ubuntu-microprofile;11.0.0-M1-ubuntu-microprofile;11.0.0-M1-jre25-Temurin-microprofile;11.0.0-M1-Temurin-microprofile;11.0.0-M1-jre25-microprofile;11.0.0-M1-microprofile;11.0.0-M1-jre25-Temurin-ubuntu;11.0.0-M1-Temurin-ubuntu;11.0.0-M1-jre25-ubuntu;11.0.0-M1-ubuntu;11.0.0-M1-jre25-Temurin;11.0.0-M1-Temurin;11.0.0-M1-jre25;11.0.0-M1
- New tags: 11.0.0-M2-jre25-Temurin-ubuntu-microprofile;11.0.0-M2-Temurin-ubuntu-microprofile;11.0.0-M2-jre25-ubuntu-microprofile;11.0.0-M2-ubuntu-microprofile;11.0.0-M2-jre25-Temurin-microprofile;11.0.0-M2-Temurin-microprofile;11.0.0-M2-jre25-microprofile;11.0.0-M2-microprofile;11.0.0-M2-jre25-Temurin-ubuntu;11.0.0-M2-Temurin-ubuntu;11.0.0-M2-jre25-ubuntu;11.0.0-M2-ubuntu;11.0.0-M2-jre25-Temurin;11.0.0-M2-Temurin;11.0.0-M2-jre25;11.0.0-M2;11.0-jre25-Temurin-ubuntu-microprofile;11.0-Temurin-ubuntu-microprofile;11.0-jre25-ubuntu-microprofile;11.0-ubuntu-microprofile;11.0-jre25-Temurin-microprofile;11.0-Temurin-microprofile;11.0-jre25-microprofile;11.0-microprofile;11.0-jre25-Temurin-ubuntu;11.0-Temurin-ubuntu;11.0-jre25-ubuntu;11.0-ubuntu;11.0-jre25-Temurin;11.0-Temurin;11.0-jre25;11.0;11-jre25-Temurin-ubuntu-microprofile;11-Temurin-ubuntu-microprofile;11-jre25-ubuntu-microprofile;11-ubuntu-microprofile;11-jre25-Temurin-microprofile;11-Temurin-microprofile;11-jre25-microprofile;11-microprofile;11-jre25-Temurin-ubuntu;11-Temurin-ubuntu;11-jre25-ubuntu;11-ubuntu;11-jre25-Temurin;11-Temurin;11-jre25;11
- Explicit moved aliases: 11.0-jre25-Temurin-ubuntu-microprofile;11.0-Temurin-ubuntu-microprofile;11.0-jre25-ubuntu-microprofile;11.0-ubuntu-microprofile;11.0-jre25-Temurin-microprofile;11.0-Temurin-microprofile;11.0-jre25-microprofile;11.0-microprofile;11.0-jre25-Temurin-ubuntu;11.0-Temurin-ubuntu;11.0-jre25-ubuntu;11.0-ubuntu;11.0-jre25-Temurin;11.0-Temurin;11.0-jre25;11.0;11-jre25-Temurin-ubuntu-microprofile;11-Temurin-ubuntu-microprofile;11-jre25-ubuntu-microprofile;11-ubuntu-microprofile;11-jre25-Temurin-microprofile;11-Temurin-microprofile;11-jre25-microprofile;11-microprofile;11-jre25-Temurin-ubuntu;11-Temurin-ubuntu;11-jre25-ubuntu;11-ubuntu;11-jre25-Temurin;11-Temurin;11-jre25;11
- Directories: `TomEE-11.0/jre25/Temurin/ubuntu/microprofile` → `TomEE-11.0/jre25/Temurin/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Temurin/ubuntu/plume

- Original tags: 11.0.0-M1-jre25-Temurin-ubuntu-plume;11.0.0-M1-Temurin-ubuntu-plume;11.0.0-M1-jre25-ubuntu-plume;11.0.0-M1-ubuntu-plume;11.0.0-M1-jre25-Temurin-plume;11.0.0-M1-Temurin-plume;11.0.0-M1-jre25-plume;11.0.0-M1-plume;11.0-jre25-Temurin-ubuntu-plume;11.0-Temurin-ubuntu-plume;11.0-jre25-ubuntu-plume;11.0-ubuntu-plume;11.0-jre25-Temurin-plume;11.0-Temurin-plume;11.0-jre25-plume;11.0-plume;11-jre25-Temurin-ubuntu-plume;11-Temurin-ubuntu-plume;11-jre25-ubuntu-plume;11-ubuntu-plume;11-jre25-Temurin-plume;11-Temurin-plume;11-jre25-plume;11-plume
- Retained tags: 11.0.0-M1-jre25-Temurin-ubuntu-plume;11.0.0-M1-Temurin-ubuntu-plume;11.0.0-M1-jre25-ubuntu-plume;11.0.0-M1-ubuntu-plume;11.0.0-M1-jre25-Temurin-plume;11.0.0-M1-Temurin-plume;11.0.0-M1-jre25-plume;11.0.0-M1-plume
- New tags: 11.0.0-M2-jre25-Temurin-ubuntu-plume;11.0.0-M2-Temurin-ubuntu-plume;11.0.0-M2-jre25-ubuntu-plume;11.0.0-M2-ubuntu-plume;11.0.0-M2-jre25-Temurin-plume;11.0.0-M2-Temurin-plume;11.0.0-M2-jre25-plume;11.0.0-M2-plume;11.0-jre25-Temurin-ubuntu-plume;11.0-Temurin-ubuntu-plume;11.0-jre25-ubuntu-plume;11.0-ubuntu-plume;11.0-jre25-Temurin-plume;11.0-Temurin-plume;11.0-jre25-plume;11.0-plume;11-jre25-Temurin-ubuntu-plume;11-Temurin-ubuntu-plume;11-jre25-ubuntu-plume;11-ubuntu-plume;11-jre25-Temurin-plume;11-Temurin-plume;11-jre25-plume;11-plume
- Explicit moved aliases: 11.0-jre25-Temurin-ubuntu-plume;11.0-Temurin-ubuntu-plume;11.0-jre25-ubuntu-plume;11.0-ubuntu-plume;11.0-jre25-Temurin-plume;11.0-Temurin-plume;11.0-jre25-plume;11.0-plume;11-jre25-Temurin-ubuntu-plume;11-Temurin-ubuntu-plume;11-jre25-ubuntu-plume;11-ubuntu-plume;11-jre25-Temurin-plume;11-Temurin-plume;11-jre25-plume;11-plume
- Directories: `TomEE-11.0/jre25/Temurin/ubuntu/plume` → `TomEE-11.0/jre25/Temurin/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Temurin/ubuntu/plus

- Original tags: 11.0.0-M1-jre25-Temurin-ubuntu-plus;11.0.0-M1-Temurin-ubuntu-plus;11.0.0-M1-jre25-ubuntu-plus;11.0.0-M1-ubuntu-plus;11.0.0-M1-jre25-Temurin-plus;11.0.0-M1-Temurin-plus;11.0.0-M1-jre25-plus;11.0.0-M1-plus;11.0-jre25-Temurin-ubuntu-plus;11.0-Temurin-ubuntu-plus;11.0-jre25-ubuntu-plus;11.0-ubuntu-plus;11.0-jre25-Temurin-plus;11.0-Temurin-plus;11.0-jre25-plus;11.0-plus;11-jre25-Temurin-ubuntu-plus;11-Temurin-ubuntu-plus;11-jre25-ubuntu-plus;11-ubuntu-plus;11-jre25-Temurin-plus;11-Temurin-plus;11-jre25-plus;11-plus
- Retained tags: 11.0.0-M1-jre25-Temurin-ubuntu-plus;11.0.0-M1-Temurin-ubuntu-plus;11.0.0-M1-jre25-ubuntu-plus;11.0.0-M1-ubuntu-plus;11.0.0-M1-jre25-Temurin-plus;11.0.0-M1-Temurin-plus;11.0.0-M1-jre25-plus;11.0.0-M1-plus
- New tags: 11.0.0-M2-jre25-Temurin-ubuntu-plus;11.0.0-M2-Temurin-ubuntu-plus;11.0.0-M2-jre25-ubuntu-plus;11.0.0-M2-ubuntu-plus;11.0.0-M2-jre25-Temurin-plus;11.0.0-M2-Temurin-plus;11.0.0-M2-jre25-plus;11.0.0-M2-plus;11.0-jre25-Temurin-ubuntu-plus;11.0-Temurin-ubuntu-plus;11.0-jre25-ubuntu-plus;11.0-ubuntu-plus;11.0-jre25-Temurin-plus;11.0-Temurin-plus;11.0-jre25-plus;11.0-plus;11-jre25-Temurin-ubuntu-plus;11-Temurin-ubuntu-plus;11-jre25-ubuntu-plus;11-ubuntu-plus;11-jre25-Temurin-plus;11-Temurin-plus;11-jre25-plus;11-plus
- Explicit moved aliases: 11.0-jre25-Temurin-ubuntu-plus;11.0-Temurin-ubuntu-plus;11.0-jre25-ubuntu-plus;11.0-ubuntu-plus;11.0-jre25-Temurin-plus;11.0-Temurin-plus;11.0-jre25-plus;11.0-plus;11-jre25-Temurin-ubuntu-plus;11-Temurin-ubuntu-plus;11-jre25-ubuntu-plus;11-ubuntu-plus;11-jre25-Temurin-plus;11-Temurin-plus;11-jre25-plus;11-plus
- Directories: `TomEE-11.0/jre25/Temurin/ubuntu/plus` → `TomEE-11.0/jre25/Temurin/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Temurin/ubuntu/webprofile

- Original tags: 11.0.0-M1-jre25-Temurin-ubuntu-webprofile;11.0.0-M1-Temurin-ubuntu-webprofile;11.0.0-M1-jre25-ubuntu-webprofile;11.0.0-M1-ubuntu-webprofile;11.0.0-M1-jre25-Temurin-webprofile;11.0.0-M1-Temurin-webprofile;11.0.0-M1-jre25-webprofile;11.0.0-M1-webprofile;11.0-jre25-Temurin-ubuntu-webprofile;11.0-Temurin-ubuntu-webprofile;11.0-jre25-ubuntu-webprofile;11.0-ubuntu-webprofile;11.0-jre25-Temurin-webprofile;11.0-Temurin-webprofile;11.0-jre25-webprofile;11.0-webprofile;11-jre25-Temurin-ubuntu-webprofile;11-Temurin-ubuntu-webprofile;11-jre25-ubuntu-webprofile;11-ubuntu-webprofile;11-jre25-Temurin-webprofile;11-Temurin-webprofile;11-jre25-webprofile;11-webprofile
- Retained tags: 11.0.0-M1-jre25-Temurin-ubuntu-webprofile;11.0.0-M1-Temurin-ubuntu-webprofile;11.0.0-M1-jre25-ubuntu-webprofile;11.0.0-M1-ubuntu-webprofile;11.0.0-M1-jre25-Temurin-webprofile;11.0.0-M1-Temurin-webprofile;11.0.0-M1-jre25-webprofile;11.0.0-M1-webprofile
- New tags: 11.0.0-M2-jre25-Temurin-ubuntu-webprofile;11.0.0-M2-Temurin-ubuntu-webprofile;11.0.0-M2-jre25-ubuntu-webprofile;11.0.0-M2-ubuntu-webprofile;11.0.0-M2-jre25-Temurin-webprofile;11.0.0-M2-Temurin-webprofile;11.0.0-M2-jre25-webprofile;11.0.0-M2-webprofile;11.0-jre25-Temurin-ubuntu-webprofile;11.0-Temurin-ubuntu-webprofile;11.0-jre25-ubuntu-webprofile;11.0-ubuntu-webprofile;11.0-jre25-Temurin-webprofile;11.0-Temurin-webprofile;11.0-jre25-webprofile;11.0-webprofile;11-jre25-Temurin-ubuntu-webprofile;11-Temurin-ubuntu-webprofile;11-jre25-ubuntu-webprofile;11-ubuntu-webprofile;11-jre25-Temurin-webprofile;11-Temurin-webprofile;11-jre25-webprofile;11-webprofile
- Explicit moved aliases: 11.0-jre25-Temurin-ubuntu-webprofile;11.0-Temurin-ubuntu-webprofile;11.0-jre25-ubuntu-webprofile;11.0-ubuntu-webprofile;11.0-jre25-Temurin-webprofile;11.0-Temurin-webprofile;11.0-jre25-webprofile;11.0-webprofile;11-jre25-Temurin-ubuntu-webprofile;11-Temurin-ubuntu-webprofile;11-jre25-ubuntu-webprofile;11-ubuntu-webprofile;11-jre25-Temurin-webprofile;11-Temurin-webprofile;11-jre25-webprofile;11-webprofile
- Directories: `TomEE-11.0/jre25/Temurin/ubuntu/webprofile` → `TomEE-11.0/jre25/Temurin/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Temurin/alpine/microprofile

- Original tags: 11.0.0-M1-jre25-Temurin-alpine-microprofile;11.0.0-M1-Temurin-alpine-microprofile;11.0.0-M1-jre25-alpine-microprofile;11.0.0-M1-alpine-microprofile;11.0.0-M1-jre25-Temurin-alpine;11.0.0-M1-Temurin-alpine;11.0.0-M1-jre25-alpine;11.0.0-M1-alpine;11.0-jre25-Temurin-alpine-microprofile;11.0-Temurin-alpine-microprofile;11.0-jre25-alpine-microprofile;11.0-alpine-microprofile;11.0-jre25-Temurin-alpine;11.0-Temurin-alpine;11.0-jre25-alpine;11.0-alpine;11-jre25-Temurin-alpine-microprofile;11-Temurin-alpine-microprofile;11-jre25-alpine-microprofile;11-alpine-microprofile;11-jre25-Temurin-alpine;11-Temurin-alpine;11-jre25-alpine;11-alpine
- Retained tags: 11.0.0-M1-jre25-Temurin-alpine-microprofile;11.0.0-M1-Temurin-alpine-microprofile;11.0.0-M1-jre25-alpine-microprofile;11.0.0-M1-alpine-microprofile;11.0.0-M1-jre25-Temurin-alpine;11.0.0-M1-Temurin-alpine;11.0.0-M1-jre25-alpine;11.0.0-M1-alpine
- New tags: 11.0.0-M2-jre25-Temurin-alpine-microprofile;11.0.0-M2-Temurin-alpine-microprofile;11.0.0-M2-jre25-alpine-microprofile;11.0.0-M2-alpine-microprofile;11.0.0-M2-jre25-Temurin-alpine;11.0.0-M2-Temurin-alpine;11.0.0-M2-jre25-alpine;11.0.0-M2-alpine;11.0-jre25-Temurin-alpine-microprofile;11.0-Temurin-alpine-microprofile;11.0-jre25-alpine-microprofile;11.0-alpine-microprofile;11.0-jre25-Temurin-alpine;11.0-Temurin-alpine;11.0-jre25-alpine;11.0-alpine;11-jre25-Temurin-alpine-microprofile;11-Temurin-alpine-microprofile;11-jre25-alpine-microprofile;11-alpine-microprofile;11-jre25-Temurin-alpine;11-Temurin-alpine;11-jre25-alpine;11-alpine
- Explicit moved aliases: 11.0-jre25-Temurin-alpine-microprofile;11.0-Temurin-alpine-microprofile;11.0-jre25-alpine-microprofile;11.0-alpine-microprofile;11.0-jre25-Temurin-alpine;11.0-Temurin-alpine;11.0-jre25-alpine;11.0-alpine;11-jre25-Temurin-alpine-microprofile;11-Temurin-alpine-microprofile;11-jre25-alpine-microprofile;11-alpine-microprofile;11-jre25-Temurin-alpine;11-Temurin-alpine;11-jre25-alpine;11-alpine
- Directories: `TomEE-11.0/jre25/Temurin/alpine/microprofile` → `TomEE-11.0/jre25/Temurin/alpine/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Temurin/alpine/plume

- Original tags: 11.0.0-M1-jre25-Temurin-alpine-plume;11.0.0-M1-Temurin-alpine-plume;11.0.0-M1-jre25-alpine-plume;11.0.0-M1-alpine-plume;11.0-jre25-Temurin-alpine-plume;11.0-Temurin-alpine-plume;11.0-jre25-alpine-plume;11.0-alpine-plume;11-jre25-Temurin-alpine-plume;11-Temurin-alpine-plume;11-jre25-alpine-plume;11-alpine-plume
- Retained tags: 11.0.0-M1-jre25-Temurin-alpine-plume;11.0.0-M1-Temurin-alpine-plume;11.0.0-M1-jre25-alpine-plume;11.0.0-M1-alpine-plume
- New tags: 11.0.0-M2-jre25-Temurin-alpine-plume;11.0.0-M2-Temurin-alpine-plume;11.0.0-M2-jre25-alpine-plume;11.0.0-M2-alpine-plume;11.0-jre25-Temurin-alpine-plume;11.0-Temurin-alpine-plume;11.0-jre25-alpine-plume;11.0-alpine-plume;11-jre25-Temurin-alpine-plume;11-Temurin-alpine-plume;11-jre25-alpine-plume;11-alpine-plume
- Explicit moved aliases: 11.0-jre25-Temurin-alpine-plume;11.0-Temurin-alpine-plume;11.0-jre25-alpine-plume;11.0-alpine-plume;11-jre25-Temurin-alpine-plume;11-Temurin-alpine-plume;11-jre25-alpine-plume;11-alpine-plume
- Directories: `TomEE-11.0/jre25/Temurin/alpine/plume` → `TomEE-11.0/jre25/Temurin/alpine/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Temurin/alpine/plus

- Original tags: 11.0.0-M1-jre25-Temurin-alpine-plus;11.0.0-M1-Temurin-alpine-plus;11.0.0-M1-jre25-alpine-plus;11.0.0-M1-alpine-plus;11.0-jre25-Temurin-alpine-plus;11.0-Temurin-alpine-plus;11.0-jre25-alpine-plus;11.0-alpine-plus;11-jre25-Temurin-alpine-plus;11-Temurin-alpine-plus;11-jre25-alpine-plus;11-alpine-plus
- Retained tags: 11.0.0-M1-jre25-Temurin-alpine-plus;11.0.0-M1-Temurin-alpine-plus;11.0.0-M1-jre25-alpine-plus;11.0.0-M1-alpine-plus
- New tags: 11.0.0-M2-jre25-Temurin-alpine-plus;11.0.0-M2-Temurin-alpine-plus;11.0.0-M2-jre25-alpine-plus;11.0.0-M2-alpine-plus;11.0-jre25-Temurin-alpine-plus;11.0-Temurin-alpine-plus;11.0-jre25-alpine-plus;11.0-alpine-plus;11-jre25-Temurin-alpine-plus;11-Temurin-alpine-plus;11-jre25-alpine-plus;11-alpine-plus
- Explicit moved aliases: 11.0-jre25-Temurin-alpine-plus;11.0-Temurin-alpine-plus;11.0-jre25-alpine-plus;11.0-alpine-plus;11-jre25-Temurin-alpine-plus;11-Temurin-alpine-plus;11-jre25-alpine-plus;11-alpine-plus
- Directories: `TomEE-11.0/jre25/Temurin/alpine/plus` → `TomEE-11.0/jre25/Temurin/alpine/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Temurin/alpine/webprofile

- Original tags: 11.0.0-M1-jre25-Temurin-alpine-webprofile;11.0.0-M1-Temurin-alpine-webprofile;11.0.0-M1-jre25-alpine-webprofile;11.0.0-M1-alpine-webprofile;11.0-jre25-Temurin-alpine-webprofile;11.0-Temurin-alpine-webprofile;11.0-jre25-alpine-webprofile;11.0-alpine-webprofile;11-jre25-Temurin-alpine-webprofile;11-Temurin-alpine-webprofile;11-jre25-alpine-webprofile;11-alpine-webprofile
- Retained tags: 11.0.0-M1-jre25-Temurin-alpine-webprofile;11.0.0-M1-Temurin-alpine-webprofile;11.0.0-M1-jre25-alpine-webprofile;11.0.0-M1-alpine-webprofile
- New tags: 11.0.0-M2-jre25-Temurin-alpine-webprofile;11.0.0-M2-Temurin-alpine-webprofile;11.0.0-M2-jre25-alpine-webprofile;11.0.0-M2-alpine-webprofile;11.0-jre25-Temurin-alpine-webprofile;11.0-Temurin-alpine-webprofile;11.0-jre25-alpine-webprofile;11.0-alpine-webprofile;11-jre25-Temurin-alpine-webprofile;11-Temurin-alpine-webprofile;11-jre25-alpine-webprofile;11-alpine-webprofile
- Explicit moved aliases: 11.0-jre25-Temurin-alpine-webprofile;11.0-Temurin-alpine-webprofile;11.0-jre25-alpine-webprofile;11.0-alpine-webprofile;11-jre25-Temurin-alpine-webprofile;11-Temurin-alpine-webprofile;11-jre25-alpine-webprofile;11-alpine-webprofile
- Directories: `TomEE-11.0/jre25/Temurin/alpine/webprofile` → `TomEE-11.0/jre25/Temurin/alpine/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Semeru/ubuntu/microprofile

- Original tags: 11.0.0-M1-jre25-Semeru-ubuntu-microprofile;11.0.0-M1-Semeru-ubuntu-microprofile;11.0.0-M1-jre25-Semeru-microprofile;11.0.0-M1-Semeru-microprofile;11.0.0-M1-jre25-Semeru-ubuntu;11.0.0-M1-Semeru-ubuntu;11.0.0-M1-jre25-Semeru;11.0.0-M1-Semeru;11.0-jre25-Semeru-ubuntu-microprofile;11.0-Semeru-ubuntu-microprofile;11.0-jre25-Semeru-microprofile;11.0-Semeru-microprofile;11.0-jre25-Semeru-ubuntu;11.0-Semeru-ubuntu;11.0-jre25-Semeru;11.0-Semeru;11-jre25-Semeru-ubuntu-microprofile;11-Semeru-ubuntu-microprofile;11-jre25-Semeru-microprofile;11-Semeru-microprofile;11-jre25-Semeru-ubuntu;11-Semeru-ubuntu;11-jre25-Semeru;11-Semeru
- Retained tags: 11.0.0-M1-jre25-Semeru-ubuntu-microprofile;11.0.0-M1-Semeru-ubuntu-microprofile;11.0.0-M1-jre25-Semeru-microprofile;11.0.0-M1-Semeru-microprofile;11.0.0-M1-jre25-Semeru-ubuntu;11.0.0-M1-Semeru-ubuntu;11.0.0-M1-jre25-Semeru;11.0.0-M1-Semeru
- New tags: 11.0.0-M2-jre25-Semeru-ubuntu-microprofile;11.0.0-M2-Semeru-ubuntu-microprofile;11.0.0-M2-jre25-Semeru-microprofile;11.0.0-M2-Semeru-microprofile;11.0.0-M2-jre25-Semeru-ubuntu;11.0.0-M2-Semeru-ubuntu;11.0.0-M2-jre25-Semeru;11.0.0-M2-Semeru;11.0-jre25-Semeru-ubuntu-microprofile;11.0-Semeru-ubuntu-microprofile;11.0-jre25-Semeru-microprofile;11.0-Semeru-microprofile;11.0-jre25-Semeru-ubuntu;11.0-Semeru-ubuntu;11.0-jre25-Semeru;11.0-Semeru;11-jre25-Semeru-ubuntu-microprofile;11-Semeru-ubuntu-microprofile;11-jre25-Semeru-microprofile;11-Semeru-microprofile;11-jre25-Semeru-ubuntu;11-Semeru-ubuntu;11-jre25-Semeru;11-Semeru
- Explicit moved aliases: 11.0-jre25-Semeru-ubuntu-microprofile;11.0-Semeru-ubuntu-microprofile;11.0-jre25-Semeru-microprofile;11.0-Semeru-microprofile;11.0-jre25-Semeru-ubuntu;11.0-Semeru-ubuntu;11.0-jre25-Semeru;11.0-Semeru;11-jre25-Semeru-ubuntu-microprofile;11-Semeru-ubuntu-microprofile;11-jre25-Semeru-microprofile;11-Semeru-microprofile;11-jre25-Semeru-ubuntu;11-Semeru-ubuntu;11-jre25-Semeru;11-Semeru
- Directories: `TomEE-11.0/jre25/Semeru/ubuntu/microprofile` → `TomEE-11.0/jre25/Semeru/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Semeru/ubuntu/plume

- Original tags: 11.0.0-M1-jre25-Semeru-ubuntu-plume;11.0.0-M1-Semeru-ubuntu-plume;11.0.0-M1-jre25-Semeru-plume;11.0.0-M1-Semeru-plume;11.0-jre25-Semeru-ubuntu-plume;11.0-Semeru-ubuntu-plume;11.0-jre25-Semeru-plume;11.0-Semeru-plume;11-jre25-Semeru-ubuntu-plume;11-Semeru-ubuntu-plume;11-jre25-Semeru-plume;11-Semeru-plume
- Retained tags: 11.0.0-M1-jre25-Semeru-ubuntu-plume;11.0.0-M1-Semeru-ubuntu-plume;11.0.0-M1-jre25-Semeru-plume;11.0.0-M1-Semeru-plume
- New tags: 11.0.0-M2-jre25-Semeru-ubuntu-plume;11.0.0-M2-Semeru-ubuntu-plume;11.0.0-M2-jre25-Semeru-plume;11.0.0-M2-Semeru-plume;11.0-jre25-Semeru-ubuntu-plume;11.0-Semeru-ubuntu-plume;11.0-jre25-Semeru-plume;11.0-Semeru-plume;11-jre25-Semeru-ubuntu-plume;11-Semeru-ubuntu-plume;11-jre25-Semeru-plume;11-Semeru-plume
- Explicit moved aliases: 11.0-jre25-Semeru-ubuntu-plume;11.0-Semeru-ubuntu-plume;11.0-jre25-Semeru-plume;11.0-Semeru-plume;11-jre25-Semeru-ubuntu-plume;11-Semeru-ubuntu-plume;11-jre25-Semeru-plume;11-Semeru-plume
- Directories: `TomEE-11.0/jre25/Semeru/ubuntu/plume` → `TomEE-11.0/jre25/Semeru/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Semeru/ubuntu/plus

- Original tags: 11.0.0-M1-jre25-Semeru-ubuntu-plus;11.0.0-M1-Semeru-ubuntu-plus;11.0.0-M1-jre25-Semeru-plus;11.0.0-M1-Semeru-plus;11.0-jre25-Semeru-ubuntu-plus;11.0-Semeru-ubuntu-plus;11.0-jre25-Semeru-plus;11.0-Semeru-plus;11-jre25-Semeru-ubuntu-plus;11-Semeru-ubuntu-plus;11-jre25-Semeru-plus;11-Semeru-plus
- Retained tags: 11.0.0-M1-jre25-Semeru-ubuntu-plus;11.0.0-M1-Semeru-ubuntu-plus;11.0.0-M1-jre25-Semeru-plus;11.0.0-M1-Semeru-plus
- New tags: 11.0.0-M2-jre25-Semeru-ubuntu-plus;11.0.0-M2-Semeru-ubuntu-plus;11.0.0-M2-jre25-Semeru-plus;11.0.0-M2-Semeru-plus;11.0-jre25-Semeru-ubuntu-plus;11.0-Semeru-ubuntu-plus;11.0-jre25-Semeru-plus;11.0-Semeru-plus;11-jre25-Semeru-ubuntu-plus;11-Semeru-ubuntu-plus;11-jre25-Semeru-plus;11-Semeru-plus
- Explicit moved aliases: 11.0-jre25-Semeru-ubuntu-plus;11.0-Semeru-ubuntu-plus;11.0-jre25-Semeru-plus;11.0-Semeru-plus;11-jre25-Semeru-ubuntu-plus;11-Semeru-ubuntu-plus;11-jre25-Semeru-plus;11-Semeru-plus
- Directories: `TomEE-11.0/jre25/Semeru/ubuntu/plus` → `TomEE-11.0/jre25/Semeru/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre25/Semeru/ubuntu/webprofile

- Original tags: 11.0.0-M1-jre25-Semeru-ubuntu-webprofile;11.0.0-M1-Semeru-ubuntu-webprofile;11.0.0-M1-jre25-Semeru-webprofile;11.0.0-M1-Semeru-webprofile;11.0-jre25-Semeru-ubuntu-webprofile;11.0-Semeru-ubuntu-webprofile;11.0-jre25-Semeru-webprofile;11.0-Semeru-webprofile;11-jre25-Semeru-ubuntu-webprofile;11-Semeru-ubuntu-webprofile;11-jre25-Semeru-webprofile;11-Semeru-webprofile
- Retained tags: 11.0.0-M1-jre25-Semeru-ubuntu-webprofile;11.0.0-M1-Semeru-ubuntu-webprofile;11.0.0-M1-jre25-Semeru-webprofile;11.0.0-M1-Semeru-webprofile
- New tags: 11.0.0-M2-jre25-Semeru-ubuntu-webprofile;11.0.0-M2-Semeru-ubuntu-webprofile;11.0.0-M2-jre25-Semeru-webprofile;11.0.0-M2-Semeru-webprofile;11.0-jre25-Semeru-ubuntu-webprofile;11.0-Semeru-ubuntu-webprofile;11.0-jre25-Semeru-webprofile;11.0-Semeru-webprofile;11-jre25-Semeru-ubuntu-webprofile;11-Semeru-ubuntu-webprofile;11-jre25-Semeru-webprofile;11-Semeru-webprofile
- Explicit moved aliases: 11.0-jre25-Semeru-ubuntu-webprofile;11.0-Semeru-ubuntu-webprofile;11.0-jre25-Semeru-webprofile;11.0-Semeru-webprofile;11-jre25-Semeru-ubuntu-webprofile;11-Semeru-ubuntu-webprofile;11-jre25-Semeru-webprofile;11-Semeru-webprofile
- Directories: `TomEE-11.0/jre25/Semeru/ubuntu/webprofile` → `TomEE-11.0/jre25/Semeru/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Temurin/ubuntu/microprofile

- Original tags: 11.0.0-M1-jre21-Temurin-ubuntu-microprofile;11.0.0-M1-jre21-ubuntu-microprofile;11.0.0-M1-jre21-Temurin-microprofile;11.0.0-M1-jre21-microprofile;11.0.0-M1-jre21-Temurin-ubuntu;11.0.0-M1-jre21-ubuntu;11.0.0-M1-jre21-Temurin;11.0.0-M1-jre21;11.0-jre21-Temurin-ubuntu-microprofile;11.0-jre21-ubuntu-microprofile;11.0-jre21-Temurin-microprofile;11.0-jre21-microprofile;11.0-jre21-Temurin-ubuntu;11.0-jre21-ubuntu;11.0-jre21-Temurin;11.0-jre21;11-jre21-Temurin-ubuntu-microprofile;11-jre21-ubuntu-microprofile;11-jre21-Temurin-microprofile;11-jre21-microprofile;11-jre21-Temurin-ubuntu;11-jre21-ubuntu;11-jre21-Temurin;11-jre21
- Retained tags: 11.0.0-M1-jre21-Temurin-ubuntu-microprofile;11.0.0-M1-jre21-ubuntu-microprofile;11.0.0-M1-jre21-Temurin-microprofile;11.0.0-M1-jre21-microprofile;11.0.0-M1-jre21-Temurin-ubuntu;11.0.0-M1-jre21-ubuntu;11.0.0-M1-jre21-Temurin;11.0.0-M1-jre21
- New tags: 11.0.0-M2-jre21-Temurin-ubuntu-microprofile;11.0.0-M2-jre21-ubuntu-microprofile;11.0.0-M2-jre21-Temurin-microprofile;11.0.0-M2-jre21-microprofile;11.0.0-M2-jre21-Temurin-ubuntu;11.0.0-M2-jre21-ubuntu;11.0.0-M2-jre21-Temurin;11.0.0-M2-jre21;11.0-jre21-Temurin-ubuntu-microprofile;11.0-jre21-ubuntu-microprofile;11.0-jre21-Temurin-microprofile;11.0-jre21-microprofile;11.0-jre21-Temurin-ubuntu;11.0-jre21-ubuntu;11.0-jre21-Temurin;11.0-jre21;11-jre21-Temurin-ubuntu-microprofile;11-jre21-ubuntu-microprofile;11-jre21-Temurin-microprofile;11-jre21-microprofile;11-jre21-Temurin-ubuntu;11-jre21-ubuntu;11-jre21-Temurin;11-jre21
- Explicit moved aliases: 11.0-jre21-Temurin-ubuntu-microprofile;11.0-jre21-ubuntu-microprofile;11.0-jre21-Temurin-microprofile;11.0-jre21-microprofile;11.0-jre21-Temurin-ubuntu;11.0-jre21-ubuntu;11.0-jre21-Temurin;11.0-jre21;11-jre21-Temurin-ubuntu-microprofile;11-jre21-ubuntu-microprofile;11-jre21-Temurin-microprofile;11-jre21-microprofile;11-jre21-Temurin-ubuntu;11-jre21-ubuntu;11-jre21-Temurin;11-jre21
- Directories: `TomEE-11.0/jre21/Temurin/ubuntu/microprofile` → `TomEE-11.0/jre21/Temurin/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Temurin/ubuntu/plume

- Original tags: 11.0.0-M1-jre21-Temurin-ubuntu-plume;11.0.0-M1-jre21-ubuntu-plume;11.0.0-M1-jre21-Temurin-plume;11.0.0-M1-jre21-plume;11.0-jre21-Temurin-ubuntu-plume;11.0-jre21-ubuntu-plume;11.0-jre21-Temurin-plume;11.0-jre21-plume;11-jre21-Temurin-ubuntu-plume;11-jre21-ubuntu-plume;11-jre21-Temurin-plume;11-jre21-plume
- Retained tags: 11.0.0-M1-jre21-Temurin-ubuntu-plume;11.0.0-M1-jre21-ubuntu-plume;11.0.0-M1-jre21-Temurin-plume;11.0.0-M1-jre21-plume
- New tags: 11.0.0-M2-jre21-Temurin-ubuntu-plume;11.0.0-M2-jre21-ubuntu-plume;11.0.0-M2-jre21-Temurin-plume;11.0.0-M2-jre21-plume;11.0-jre21-Temurin-ubuntu-plume;11.0-jre21-ubuntu-plume;11.0-jre21-Temurin-plume;11.0-jre21-plume;11-jre21-Temurin-ubuntu-plume;11-jre21-ubuntu-plume;11-jre21-Temurin-plume;11-jre21-plume
- Explicit moved aliases: 11.0-jre21-Temurin-ubuntu-plume;11.0-jre21-ubuntu-plume;11.0-jre21-Temurin-plume;11.0-jre21-plume;11-jre21-Temurin-ubuntu-plume;11-jre21-ubuntu-plume;11-jre21-Temurin-plume;11-jre21-plume
- Directories: `TomEE-11.0/jre21/Temurin/ubuntu/plume` → `TomEE-11.0/jre21/Temurin/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Temurin/ubuntu/plus

- Original tags: 11.0.0-M1-jre21-Temurin-ubuntu-plus;11.0.0-M1-jre21-ubuntu-plus;11.0.0-M1-jre21-Temurin-plus;11.0.0-M1-jre21-plus;11.0-jre21-Temurin-ubuntu-plus;11.0-jre21-ubuntu-plus;11.0-jre21-Temurin-plus;11.0-jre21-plus;11-jre21-Temurin-ubuntu-plus;11-jre21-ubuntu-plus;11-jre21-Temurin-plus;11-jre21-plus
- Retained tags: 11.0.0-M1-jre21-Temurin-ubuntu-plus;11.0.0-M1-jre21-ubuntu-plus;11.0.0-M1-jre21-Temurin-plus;11.0.0-M1-jre21-plus
- New tags: 11.0.0-M2-jre21-Temurin-ubuntu-plus;11.0.0-M2-jre21-ubuntu-plus;11.0.0-M2-jre21-Temurin-plus;11.0.0-M2-jre21-plus;11.0-jre21-Temurin-ubuntu-plus;11.0-jre21-ubuntu-plus;11.0-jre21-Temurin-plus;11.0-jre21-plus;11-jre21-Temurin-ubuntu-plus;11-jre21-ubuntu-plus;11-jre21-Temurin-plus;11-jre21-plus
- Explicit moved aliases: 11.0-jre21-Temurin-ubuntu-plus;11.0-jre21-ubuntu-plus;11.0-jre21-Temurin-plus;11.0-jre21-plus;11-jre21-Temurin-ubuntu-plus;11-jre21-ubuntu-plus;11-jre21-Temurin-plus;11-jre21-plus
- Directories: `TomEE-11.0/jre21/Temurin/ubuntu/plus` → `TomEE-11.0/jre21/Temurin/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Temurin/ubuntu/webprofile

- Original tags: 11.0.0-M1-jre21-Temurin-ubuntu-webprofile;11.0.0-M1-jre21-ubuntu-webprofile;11.0.0-M1-jre21-Temurin-webprofile;11.0.0-M1-jre21-webprofile;11.0-jre21-Temurin-ubuntu-webprofile;11.0-jre21-ubuntu-webprofile;11.0-jre21-Temurin-webprofile;11.0-jre21-webprofile;11-jre21-Temurin-ubuntu-webprofile;11-jre21-ubuntu-webprofile;11-jre21-Temurin-webprofile;11-jre21-webprofile
- Retained tags: 11.0.0-M1-jre21-Temurin-ubuntu-webprofile;11.0.0-M1-jre21-ubuntu-webprofile;11.0.0-M1-jre21-Temurin-webprofile;11.0.0-M1-jre21-webprofile
- New tags: 11.0.0-M2-jre21-Temurin-ubuntu-webprofile;11.0.0-M2-jre21-ubuntu-webprofile;11.0.0-M2-jre21-Temurin-webprofile;11.0.0-M2-jre21-webprofile;11.0-jre21-Temurin-ubuntu-webprofile;11.0-jre21-ubuntu-webprofile;11.0-jre21-Temurin-webprofile;11.0-jre21-webprofile;11-jre21-Temurin-ubuntu-webprofile;11-jre21-ubuntu-webprofile;11-jre21-Temurin-webprofile;11-jre21-webprofile
- Explicit moved aliases: 11.0-jre21-Temurin-ubuntu-webprofile;11.0-jre21-ubuntu-webprofile;11.0-jre21-Temurin-webprofile;11.0-jre21-webprofile;11-jre21-Temurin-ubuntu-webprofile;11-jre21-ubuntu-webprofile;11-jre21-Temurin-webprofile;11-jre21-webprofile
- Directories: `TomEE-11.0/jre21/Temurin/ubuntu/webprofile` → `TomEE-11.0/jre21/Temurin/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Temurin/alpine/microprofile

- Original tags: 11.0.0-M1-jre21-Temurin-alpine-microprofile;11.0.0-M1-jre21-alpine-microprofile;11.0.0-M1-jre21-Temurin-alpine;11.0.0-M1-jre21-alpine;11.0-jre21-Temurin-alpine-microprofile;11.0-jre21-alpine-microprofile;11.0-jre21-Temurin-alpine;11.0-jre21-alpine;11-jre21-Temurin-alpine-microprofile;11-jre21-alpine-microprofile;11-jre21-Temurin-alpine;11-jre21-alpine
- Retained tags: 11.0.0-M1-jre21-Temurin-alpine-microprofile;11.0.0-M1-jre21-alpine-microprofile;11.0.0-M1-jre21-Temurin-alpine;11.0.0-M1-jre21-alpine
- New tags: 11.0.0-M2-jre21-Temurin-alpine-microprofile;11.0.0-M2-jre21-alpine-microprofile;11.0.0-M2-jre21-Temurin-alpine;11.0.0-M2-jre21-alpine;11.0-jre21-Temurin-alpine-microprofile;11.0-jre21-alpine-microprofile;11.0-jre21-Temurin-alpine;11.0-jre21-alpine;11-jre21-Temurin-alpine-microprofile;11-jre21-alpine-microprofile;11-jre21-Temurin-alpine;11-jre21-alpine
- Explicit moved aliases: 11.0-jre21-Temurin-alpine-microprofile;11.0-jre21-alpine-microprofile;11.0-jre21-Temurin-alpine;11.0-jre21-alpine;11-jre21-Temurin-alpine-microprofile;11-jre21-alpine-microprofile;11-jre21-Temurin-alpine;11-jre21-alpine
- Directories: `TomEE-11.0/jre21/Temurin/alpine/microprofile` → `TomEE-11.0/jre21/Temurin/alpine/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Temurin/alpine/plume

- Original tags: 11.0.0-M1-jre21-Temurin-alpine-plume;11.0.0-M1-jre21-alpine-plume;11.0-jre21-Temurin-alpine-plume;11.0-jre21-alpine-plume;11-jre21-Temurin-alpine-plume;11-jre21-alpine-plume
- Retained tags: 11.0.0-M1-jre21-Temurin-alpine-plume;11.0.0-M1-jre21-alpine-plume
- New tags: 11.0.0-M2-jre21-Temurin-alpine-plume;11.0.0-M2-jre21-alpine-plume;11.0-jre21-Temurin-alpine-plume;11.0-jre21-alpine-plume;11-jre21-Temurin-alpine-plume;11-jre21-alpine-plume
- Explicit moved aliases: 11.0-jre21-Temurin-alpine-plume;11.0-jre21-alpine-plume;11-jre21-Temurin-alpine-plume;11-jre21-alpine-plume
- Directories: `TomEE-11.0/jre21/Temurin/alpine/plume` → `TomEE-11.0/jre21/Temurin/alpine/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Temurin/alpine/plus

- Original tags: 11.0.0-M1-jre21-Temurin-alpine-plus;11.0.0-M1-jre21-alpine-plus;11.0-jre21-Temurin-alpine-plus;11.0-jre21-alpine-plus;11-jre21-Temurin-alpine-plus;11-jre21-alpine-plus
- Retained tags: 11.0.0-M1-jre21-Temurin-alpine-plus;11.0.0-M1-jre21-alpine-plus
- New tags: 11.0.0-M2-jre21-Temurin-alpine-plus;11.0.0-M2-jre21-alpine-plus;11.0-jre21-Temurin-alpine-plus;11.0-jre21-alpine-plus;11-jre21-Temurin-alpine-plus;11-jre21-alpine-plus
- Explicit moved aliases: 11.0-jre21-Temurin-alpine-plus;11.0-jre21-alpine-plus;11-jre21-Temurin-alpine-plus;11-jre21-alpine-plus
- Directories: `TomEE-11.0/jre21/Temurin/alpine/plus` → `TomEE-11.0/jre21/Temurin/alpine/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Temurin/alpine/webprofile

- Original tags: 11.0.0-M1-jre21-Temurin-alpine-webprofile;11.0.0-M1-jre21-alpine-webprofile;11.0-jre21-Temurin-alpine-webprofile;11.0-jre21-alpine-webprofile;11-jre21-Temurin-alpine-webprofile;11-jre21-alpine-webprofile
- Retained tags: 11.0.0-M1-jre21-Temurin-alpine-webprofile;11.0.0-M1-jre21-alpine-webprofile
- New tags: 11.0.0-M2-jre21-Temurin-alpine-webprofile;11.0.0-M2-jre21-alpine-webprofile;11.0-jre21-Temurin-alpine-webprofile;11.0-jre21-alpine-webprofile;11-jre21-Temurin-alpine-webprofile;11-jre21-alpine-webprofile
- Explicit moved aliases: 11.0-jre21-Temurin-alpine-webprofile;11.0-jre21-alpine-webprofile;11-jre21-Temurin-alpine-webprofile;11-jre21-alpine-webprofile
- Directories: `TomEE-11.0/jre21/Temurin/alpine/webprofile` → `TomEE-11.0/jre21/Temurin/alpine/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Semeru/ubuntu/microprofile

- Original tags: 11.0.0-M1-jre21-Semeru-ubuntu-microprofile;11.0.0-M1-jre21-Semeru-microprofile;11.0.0-M1-jre21-Semeru-ubuntu;11.0.0-M1-jre21-Semeru;11.0-jre21-Semeru-ubuntu-microprofile;11.0-jre21-Semeru-microprofile;11.0-jre21-Semeru-ubuntu;11.0-jre21-Semeru;11-jre21-Semeru-ubuntu-microprofile;11-jre21-Semeru-microprofile;11-jre21-Semeru-ubuntu;11-jre21-Semeru
- Retained tags: 11.0.0-M1-jre21-Semeru-ubuntu-microprofile;11.0.0-M1-jre21-Semeru-microprofile;11.0.0-M1-jre21-Semeru-ubuntu;11.0.0-M1-jre21-Semeru
- New tags: 11.0.0-M2-jre21-Semeru-ubuntu-microprofile;11.0.0-M2-jre21-Semeru-microprofile;11.0.0-M2-jre21-Semeru-ubuntu;11.0.0-M2-jre21-Semeru;11.0-jre21-Semeru-ubuntu-microprofile;11.0-jre21-Semeru-microprofile;11.0-jre21-Semeru-ubuntu;11.0-jre21-Semeru;11-jre21-Semeru-ubuntu-microprofile;11-jre21-Semeru-microprofile;11-jre21-Semeru-ubuntu;11-jre21-Semeru
- Explicit moved aliases: 11.0-jre21-Semeru-ubuntu-microprofile;11.0-jre21-Semeru-microprofile;11.0-jre21-Semeru-ubuntu;11.0-jre21-Semeru;11-jre21-Semeru-ubuntu-microprofile;11-jre21-Semeru-microprofile;11-jre21-Semeru-ubuntu;11-jre21-Semeru
- Directories: `TomEE-11.0/jre21/Semeru/ubuntu/microprofile` → `TomEE-11.0/jre21/Semeru/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Semeru/ubuntu/plume

- Original tags: 11.0.0-M1-jre21-Semeru-ubuntu-plume;11.0.0-M1-jre21-Semeru-plume;11.0-jre21-Semeru-ubuntu-plume;11.0-jre21-Semeru-plume;11-jre21-Semeru-ubuntu-plume;11-jre21-Semeru-plume
- Retained tags: 11.0.0-M1-jre21-Semeru-ubuntu-plume;11.0.0-M1-jre21-Semeru-plume
- New tags: 11.0.0-M2-jre21-Semeru-ubuntu-plume;11.0.0-M2-jre21-Semeru-plume;11.0-jre21-Semeru-ubuntu-plume;11.0-jre21-Semeru-plume;11-jre21-Semeru-ubuntu-plume;11-jre21-Semeru-plume
- Explicit moved aliases: 11.0-jre21-Semeru-ubuntu-plume;11.0-jre21-Semeru-plume;11-jre21-Semeru-ubuntu-plume;11-jre21-Semeru-plume
- Directories: `TomEE-11.0/jre21/Semeru/ubuntu/plume` → `TomEE-11.0/jre21/Semeru/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Semeru/ubuntu/plus

- Original tags: 11.0.0-M1-jre21-Semeru-ubuntu-plus;11.0.0-M1-jre21-Semeru-plus;11.0-jre21-Semeru-ubuntu-plus;11.0-jre21-Semeru-plus;11-jre21-Semeru-ubuntu-plus;11-jre21-Semeru-plus
- Retained tags: 11.0.0-M1-jre21-Semeru-ubuntu-plus;11.0.0-M1-jre21-Semeru-plus
- New tags: 11.0.0-M2-jre21-Semeru-ubuntu-plus;11.0.0-M2-jre21-Semeru-plus;11.0-jre21-Semeru-ubuntu-plus;11.0-jre21-Semeru-plus;11-jre21-Semeru-ubuntu-plus;11-jre21-Semeru-plus
- Explicit moved aliases: 11.0-jre21-Semeru-ubuntu-plus;11.0-jre21-Semeru-plus;11-jre21-Semeru-ubuntu-plus;11-jre21-Semeru-plus
- Directories: `TomEE-11.0/jre21/Semeru/ubuntu/plus` → `TomEE-11.0/jre21/Semeru/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre21/Semeru/ubuntu/webprofile

- Original tags: 11.0.0-M1-jre21-Semeru-ubuntu-webprofile;11.0.0-M1-jre21-Semeru-webprofile;11.0-jre21-Semeru-ubuntu-webprofile;11.0-jre21-Semeru-webprofile;11-jre21-Semeru-ubuntu-webprofile;11-jre21-Semeru-webprofile
- Retained tags: 11.0.0-M1-jre21-Semeru-ubuntu-webprofile;11.0.0-M1-jre21-Semeru-webprofile
- New tags: 11.0.0-M2-jre21-Semeru-ubuntu-webprofile;11.0.0-M2-jre21-Semeru-webprofile;11.0-jre21-Semeru-ubuntu-webprofile;11.0-jre21-Semeru-webprofile;11-jre21-Semeru-ubuntu-webprofile;11-jre21-Semeru-webprofile
- Explicit moved aliases: 11.0-jre21-Semeru-ubuntu-webprofile;11.0-jre21-Semeru-webprofile;11-jre21-Semeru-ubuntu-webprofile;11-jre21-Semeru-webprofile
- Directories: `TomEE-11.0/jre21/Semeru/ubuntu/webprofile` → `TomEE-11.0/jre21/Semeru/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Temurin/ubuntu/microprofile

- Original tags: 11.0.0-M1-jre17-Temurin-ubuntu-microprofile;11.0.0-M1-jre17-ubuntu-microprofile;11.0.0-M1-jre17-Temurin-microprofile;11.0.0-M1-jre17-microprofile;11.0.0-M1-jre17-Temurin-ubuntu;11.0.0-M1-jre17-ubuntu;11.0.0-M1-jre17-Temurin;11.0.0-M1-jre17;11.0-jre17-Temurin-ubuntu-microprofile;11.0-jre17-ubuntu-microprofile;11.0-jre17-Temurin-microprofile;11.0-jre17-microprofile;11.0-jre17-Temurin-ubuntu;11.0-jre17-ubuntu;11.0-jre17-Temurin;11.0-jre17;11-jre17-Temurin-ubuntu-microprofile;11-jre17-ubuntu-microprofile;11-jre17-Temurin-microprofile;11-jre17-microprofile;11-jre17-Temurin-ubuntu;11-jre17-ubuntu;11-jre17-Temurin;11-jre17
- Retained tags: 11.0.0-M1-jre17-Temurin-ubuntu-microprofile;11.0.0-M1-jre17-ubuntu-microprofile;11.0.0-M1-jre17-Temurin-microprofile;11.0.0-M1-jre17-microprofile;11.0.0-M1-jre17-Temurin-ubuntu;11.0.0-M1-jre17-ubuntu;11.0.0-M1-jre17-Temurin;11.0.0-M1-jre17
- New tags: 11.0.0-M2-jre17-Temurin-ubuntu-microprofile;11.0.0-M2-jre17-ubuntu-microprofile;11.0.0-M2-jre17-Temurin-microprofile;11.0.0-M2-jre17-microprofile;11.0.0-M2-jre17-Temurin-ubuntu;11.0.0-M2-jre17-ubuntu;11.0.0-M2-jre17-Temurin;11.0.0-M2-jre17;11.0-jre17-Temurin-ubuntu-microprofile;11.0-jre17-ubuntu-microprofile;11.0-jre17-Temurin-microprofile;11.0-jre17-microprofile;11.0-jre17-Temurin-ubuntu;11.0-jre17-ubuntu;11.0-jre17-Temurin;11.0-jre17;11-jre17-Temurin-ubuntu-microprofile;11-jre17-ubuntu-microprofile;11-jre17-Temurin-microprofile;11-jre17-microprofile;11-jre17-Temurin-ubuntu;11-jre17-ubuntu;11-jre17-Temurin;11-jre17
- Explicit moved aliases: 11.0-jre17-Temurin-ubuntu-microprofile;11.0-jre17-ubuntu-microprofile;11.0-jre17-Temurin-microprofile;11.0-jre17-microprofile;11.0-jre17-Temurin-ubuntu;11.0-jre17-ubuntu;11.0-jre17-Temurin;11.0-jre17;11-jre17-Temurin-ubuntu-microprofile;11-jre17-ubuntu-microprofile;11-jre17-Temurin-microprofile;11-jre17-microprofile;11-jre17-Temurin-ubuntu;11-jre17-ubuntu;11-jre17-Temurin;11-jre17
- Directories: `TomEE-11.0/jre17/Temurin/ubuntu/microprofile` → `TomEE-11.0/jre17/Temurin/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Temurin/ubuntu/plume

- Original tags: 11.0.0-M1-jre17-Temurin-ubuntu-plume;11.0.0-M1-jre17-ubuntu-plume;11.0.0-M1-jre17-Temurin-plume;11.0.0-M1-jre17-plume;11.0-jre17-Temurin-ubuntu-plume;11.0-jre17-ubuntu-plume;11.0-jre17-Temurin-plume;11.0-jre17-plume;11-jre17-Temurin-ubuntu-plume;11-jre17-ubuntu-plume;11-jre17-Temurin-plume;11-jre17-plume
- Retained tags: 11.0.0-M1-jre17-Temurin-ubuntu-plume;11.0.0-M1-jre17-ubuntu-plume;11.0.0-M1-jre17-Temurin-plume;11.0.0-M1-jre17-plume
- New tags: 11.0.0-M2-jre17-Temurin-ubuntu-plume;11.0.0-M2-jre17-ubuntu-plume;11.0.0-M2-jre17-Temurin-plume;11.0.0-M2-jre17-plume;11.0-jre17-Temurin-ubuntu-plume;11.0-jre17-ubuntu-plume;11.0-jre17-Temurin-plume;11.0-jre17-plume;11-jre17-Temurin-ubuntu-plume;11-jre17-ubuntu-plume;11-jre17-Temurin-plume;11-jre17-plume
- Explicit moved aliases: 11.0-jre17-Temurin-ubuntu-plume;11.0-jre17-ubuntu-plume;11.0-jre17-Temurin-plume;11.0-jre17-plume;11-jre17-Temurin-ubuntu-plume;11-jre17-ubuntu-plume;11-jre17-Temurin-plume;11-jre17-plume
- Directories: `TomEE-11.0/jre17/Temurin/ubuntu/plume` → `TomEE-11.0/jre17/Temurin/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Temurin/ubuntu/plus

- Original tags: 11.0.0-M1-jre17-Temurin-ubuntu-plus;11.0.0-M1-jre17-ubuntu-plus;11.0.0-M1-jre17-Temurin-plus;11.0.0-M1-jre17-plus;11.0-jre17-Temurin-ubuntu-plus;11.0-jre17-ubuntu-plus;11.0-jre17-Temurin-plus;11.0-jre17-plus;11-jre17-Temurin-ubuntu-plus;11-jre17-ubuntu-plus;11-jre17-Temurin-plus;11-jre17-plus
- Retained tags: 11.0.0-M1-jre17-Temurin-ubuntu-plus;11.0.0-M1-jre17-ubuntu-plus;11.0.0-M1-jre17-Temurin-plus;11.0.0-M1-jre17-plus
- New tags: 11.0.0-M2-jre17-Temurin-ubuntu-plus;11.0.0-M2-jre17-ubuntu-plus;11.0.0-M2-jre17-Temurin-plus;11.0.0-M2-jre17-plus;11.0-jre17-Temurin-ubuntu-plus;11.0-jre17-ubuntu-plus;11.0-jre17-Temurin-plus;11.0-jre17-plus;11-jre17-Temurin-ubuntu-plus;11-jre17-ubuntu-plus;11-jre17-Temurin-plus;11-jre17-plus
- Explicit moved aliases: 11.0-jre17-Temurin-ubuntu-plus;11.0-jre17-ubuntu-plus;11.0-jre17-Temurin-plus;11.0-jre17-plus;11-jre17-Temurin-ubuntu-plus;11-jre17-ubuntu-plus;11-jre17-Temurin-plus;11-jre17-plus
- Directories: `TomEE-11.0/jre17/Temurin/ubuntu/plus` → `TomEE-11.0/jre17/Temurin/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Temurin/ubuntu/webprofile

- Original tags: 11.0.0-M1-jre17-Temurin-ubuntu-webprofile;11.0.0-M1-jre17-ubuntu-webprofile;11.0.0-M1-jre17-Temurin-webprofile;11.0.0-M1-jre17-webprofile;11.0-jre17-Temurin-ubuntu-webprofile;11.0-jre17-ubuntu-webprofile;11.0-jre17-Temurin-webprofile;11.0-jre17-webprofile;11-jre17-Temurin-ubuntu-webprofile;11-jre17-ubuntu-webprofile;11-jre17-Temurin-webprofile;11-jre17-webprofile
- Retained tags: 11.0.0-M1-jre17-Temurin-ubuntu-webprofile;11.0.0-M1-jre17-ubuntu-webprofile;11.0.0-M1-jre17-Temurin-webprofile;11.0.0-M1-jre17-webprofile
- New tags: 11.0.0-M2-jre17-Temurin-ubuntu-webprofile;11.0.0-M2-jre17-ubuntu-webprofile;11.0.0-M2-jre17-Temurin-webprofile;11.0.0-M2-jre17-webprofile;11.0-jre17-Temurin-ubuntu-webprofile;11.0-jre17-ubuntu-webprofile;11.0-jre17-Temurin-webprofile;11.0-jre17-webprofile;11-jre17-Temurin-ubuntu-webprofile;11-jre17-ubuntu-webprofile;11-jre17-Temurin-webprofile;11-jre17-webprofile
- Explicit moved aliases: 11.0-jre17-Temurin-ubuntu-webprofile;11.0-jre17-ubuntu-webprofile;11.0-jre17-Temurin-webprofile;11.0-jre17-webprofile;11-jre17-Temurin-ubuntu-webprofile;11-jre17-ubuntu-webprofile;11-jre17-Temurin-webprofile;11-jre17-webprofile
- Directories: `TomEE-11.0/jre17/Temurin/ubuntu/webprofile` → `TomEE-11.0/jre17/Temurin/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Temurin/alpine/microprofile

- Original tags: 11.0.0-M1-jre17-Temurin-alpine-microprofile;11.0.0-M1-jre17-alpine-microprofile;11.0.0-M1-jre17-Temurin-alpine;11.0.0-M1-jre17-alpine;11.0-jre17-Temurin-alpine-microprofile;11.0-jre17-alpine-microprofile;11.0-jre17-Temurin-alpine;11.0-jre17-alpine;11-jre17-Temurin-alpine-microprofile;11-jre17-alpine-microprofile;11-jre17-Temurin-alpine;11-jre17-alpine
- Retained tags: 11.0.0-M1-jre17-Temurin-alpine-microprofile;11.0.0-M1-jre17-alpine-microprofile;11.0.0-M1-jre17-Temurin-alpine;11.0.0-M1-jre17-alpine
- New tags: 11.0.0-M2-jre17-Temurin-alpine-microprofile;11.0.0-M2-jre17-alpine-microprofile;11.0.0-M2-jre17-Temurin-alpine;11.0.0-M2-jre17-alpine;11.0-jre17-Temurin-alpine-microprofile;11.0-jre17-alpine-microprofile;11.0-jre17-Temurin-alpine;11.0-jre17-alpine;11-jre17-Temurin-alpine-microprofile;11-jre17-alpine-microprofile;11-jre17-Temurin-alpine;11-jre17-alpine
- Explicit moved aliases: 11.0-jre17-Temurin-alpine-microprofile;11.0-jre17-alpine-microprofile;11.0-jre17-Temurin-alpine;11.0-jre17-alpine;11-jre17-Temurin-alpine-microprofile;11-jre17-alpine-microprofile;11-jre17-Temurin-alpine;11-jre17-alpine
- Directories: `TomEE-11.0/jre17/Temurin/alpine/microprofile` → `TomEE-11.0/jre17/Temurin/alpine/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64` → `amd64`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Temurin/alpine/plume

- Original tags: 11.0.0-M1-jre17-Temurin-alpine-plume;11.0.0-M1-jre17-alpine-plume;11.0-jre17-Temurin-alpine-plume;11.0-jre17-alpine-plume;11-jre17-Temurin-alpine-plume;11-jre17-alpine-plume
- Retained tags: 11.0.0-M1-jre17-Temurin-alpine-plume;11.0.0-M1-jre17-alpine-plume
- New tags: 11.0.0-M2-jre17-Temurin-alpine-plume;11.0.0-M2-jre17-alpine-plume;11.0-jre17-Temurin-alpine-plume;11.0-jre17-alpine-plume;11-jre17-Temurin-alpine-plume;11-jre17-alpine-plume
- Explicit moved aliases: 11.0-jre17-Temurin-alpine-plume;11.0-jre17-alpine-plume;11-jre17-Temurin-alpine-plume;11-jre17-alpine-plume
- Directories: `TomEE-11.0/jre17/Temurin/alpine/plume` → `TomEE-11.0/jre17/Temurin/alpine/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64` → `amd64`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Temurin/alpine/plus

- Original tags: 11.0.0-M1-jre17-Temurin-alpine-plus;11.0.0-M1-jre17-alpine-plus;11.0-jre17-Temurin-alpine-plus;11.0-jre17-alpine-plus;11-jre17-Temurin-alpine-plus;11-jre17-alpine-plus
- Retained tags: 11.0.0-M1-jre17-Temurin-alpine-plus;11.0.0-M1-jre17-alpine-plus
- New tags: 11.0.0-M2-jre17-Temurin-alpine-plus;11.0.0-M2-jre17-alpine-plus;11.0-jre17-Temurin-alpine-plus;11.0-jre17-alpine-plus;11-jre17-Temurin-alpine-plus;11-jre17-alpine-plus
- Explicit moved aliases: 11.0-jre17-Temurin-alpine-plus;11.0-jre17-alpine-plus;11-jre17-Temurin-alpine-plus;11-jre17-alpine-plus
- Directories: `TomEE-11.0/jre17/Temurin/alpine/plus` → `TomEE-11.0/jre17/Temurin/alpine/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64` → `amd64`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Temurin/alpine/webprofile

- Original tags: 11.0.0-M1-jre17-Temurin-alpine-webprofile;11.0.0-M1-jre17-alpine-webprofile;11.0-jre17-Temurin-alpine-webprofile;11.0-jre17-alpine-webprofile;11-jre17-Temurin-alpine-webprofile;11-jre17-alpine-webprofile
- Retained tags: 11.0.0-M1-jre17-Temurin-alpine-webprofile;11.0.0-M1-jre17-alpine-webprofile
- New tags: 11.0.0-M2-jre17-Temurin-alpine-webprofile;11.0.0-M2-jre17-alpine-webprofile;11.0-jre17-Temurin-alpine-webprofile;11.0-jre17-alpine-webprofile;11-jre17-Temurin-alpine-webprofile;11-jre17-alpine-webprofile
- Explicit moved aliases: 11.0-jre17-Temurin-alpine-webprofile;11.0-jre17-alpine-webprofile;11-jre17-Temurin-alpine-webprofile;11-jre17-alpine-webprofile
- Directories: `TomEE-11.0/jre17/Temurin/alpine/webprofile` → `TomEE-11.0/jre17/Temurin/alpine/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64` → `amd64`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Semeru/ubuntu/microprofile

- Original tags: 11.0.0-M1-jre17-Semeru-ubuntu-microprofile;11.0.0-M1-jre17-Semeru-microprofile;11.0.0-M1-jre17-Semeru-ubuntu;11.0.0-M1-jre17-Semeru;11.0-jre17-Semeru-ubuntu-microprofile;11.0-jre17-Semeru-microprofile;11.0-jre17-Semeru-ubuntu;11.0-jre17-Semeru;11-jre17-Semeru-ubuntu-microprofile;11-jre17-Semeru-microprofile;11-jre17-Semeru-ubuntu;11-jre17-Semeru
- Retained tags: 11.0.0-M1-jre17-Semeru-ubuntu-microprofile;11.0.0-M1-jre17-Semeru-microprofile;11.0.0-M1-jre17-Semeru-ubuntu;11.0.0-M1-jre17-Semeru
- New tags: 11.0.0-M2-jre17-Semeru-ubuntu-microprofile;11.0.0-M2-jre17-Semeru-microprofile;11.0.0-M2-jre17-Semeru-ubuntu;11.0.0-M2-jre17-Semeru;11.0-jre17-Semeru-ubuntu-microprofile;11.0-jre17-Semeru-microprofile;11.0-jre17-Semeru-ubuntu;11.0-jre17-Semeru;11-jre17-Semeru-ubuntu-microprofile;11-jre17-Semeru-microprofile;11-jre17-Semeru-ubuntu;11-jre17-Semeru
- Explicit moved aliases: 11.0-jre17-Semeru-ubuntu-microprofile;11.0-jre17-Semeru-microprofile;11.0-jre17-Semeru-ubuntu;11.0-jre17-Semeru;11-jre17-Semeru-ubuntu-microprofile;11-jre17-Semeru-microprofile;11-jre17-Semeru-ubuntu;11-jre17-Semeru
- Directories: `TomEE-11.0/jre17/Semeru/ubuntu/microprofile` → `TomEE-11.0/jre17/Semeru/ubuntu/microprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Semeru/ubuntu/plume

- Original tags: 11.0.0-M1-jre17-Semeru-ubuntu-plume;11.0.0-M1-jre17-Semeru-plume;11.0-jre17-Semeru-ubuntu-plume;11.0-jre17-Semeru-plume;11-jre17-Semeru-ubuntu-plume;11-jre17-Semeru-plume
- Retained tags: 11.0.0-M1-jre17-Semeru-ubuntu-plume;11.0.0-M1-jre17-Semeru-plume
- New tags: 11.0.0-M2-jre17-Semeru-ubuntu-plume;11.0.0-M2-jre17-Semeru-plume;11.0-jre17-Semeru-ubuntu-plume;11.0-jre17-Semeru-plume;11-jre17-Semeru-ubuntu-plume;11-jre17-Semeru-plume
- Explicit moved aliases: 11.0-jre17-Semeru-ubuntu-plume;11.0-jre17-Semeru-plume;11-jre17-Semeru-ubuntu-plume;11-jre17-Semeru-plume
- Directories: `TomEE-11.0/jre17/Semeru/ubuntu/plume` → `TomEE-11.0/jre17/Semeru/ubuntu/plume`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Semeru/ubuntu/plus

- Original tags: 11.0.0-M1-jre17-Semeru-ubuntu-plus;11.0.0-M1-jre17-Semeru-plus;11.0-jre17-Semeru-ubuntu-plus;11.0-jre17-Semeru-plus;11-jre17-Semeru-ubuntu-plus;11-jre17-Semeru-plus
- Retained tags: 11.0.0-M1-jre17-Semeru-ubuntu-plus;11.0.0-M1-jre17-Semeru-plus
- New tags: 11.0.0-M2-jre17-Semeru-ubuntu-plus;11.0.0-M2-jre17-Semeru-plus;11.0-jre17-Semeru-ubuntu-plus;11.0-jre17-Semeru-plus;11-jre17-Semeru-ubuntu-plus;11-jre17-Semeru-plus
- Explicit moved aliases: 11.0-jre17-Semeru-ubuntu-plus;11.0-jre17-Semeru-plus;11-jre17-Semeru-ubuntu-plus;11-jre17-Semeru-plus
- Directories: `TomEE-11.0/jre17/Semeru/ubuntu/plus` → `TomEE-11.0/jre17/Semeru/ubuntu/plus`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

### 11_0_M1_to_M2 — TomEE-11.0/jre17/Semeru/ubuntu/webprofile

- Original tags: 11.0.0-M1-jre17-Semeru-ubuntu-webprofile;11.0.0-M1-jre17-Semeru-webprofile;11.0-jre17-Semeru-ubuntu-webprofile;11.0-jre17-Semeru-webprofile;11-jre17-Semeru-ubuntu-webprofile;11-jre17-Semeru-webprofile
- Retained tags: 11.0.0-M1-jre17-Semeru-ubuntu-webprofile;11.0.0-M1-jre17-Semeru-webprofile
- New tags: 11.0.0-M2-jre17-Semeru-ubuntu-webprofile;11.0.0-M2-jre17-Semeru-webprofile;11.0-jre17-Semeru-ubuntu-webprofile;11.0-jre17-Semeru-webprofile;11-jre17-Semeru-ubuntu-webprofile;11-jre17-Semeru-webprofile
- Explicit moved aliases: 11.0-jre17-Semeru-ubuntu-webprofile;11.0-jre17-Semeru-webprofile;11-jre17-Semeru-ubuntu-webprofile;11-jre17-Semeru-webprofile
- Directories: `TomEE-11.0/jre17/Semeru/ubuntu/webprofile` → `TomEE-11.0/jre17/Semeru/ubuntu/webprofile`
- GitCommit: `3695dcec008bf611b2dbd06eb2123a7b159efc27` → `8a515bdfb91f554b66e73ac61cdeba3497c4d453`
- Architectures: `amd64;arm64v8` → `amd64;arm64v8`

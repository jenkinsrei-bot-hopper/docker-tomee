# Optional verification hardening follow-up

This is a separate proposal, not part of the TomEE 10.3.0 / 11.0.0-M2 source branch or proposed source PR.

The release bump deliberately retains the upstream recipe: download the release archive and its published SHA512 file, check that digest, and verify the detached GPG signature using the existing key list. That list already includes Markus Jung’s full signing-key fingerprint. The minimal version update does not need a verification rewrite.

A later, focused PR could evaluate importing the official [Apache TomEE KEYS](https://downloads.apache.org/tomee/KEYS) file and explicitly checking the expected release signer’s full fingerprint. This could reduce dependence on several external keyservers and make signer selection easier to audit. The tradeoff is a new signer-rotation/update responsibility, so it should be reviewed separately rather than bundled with a release bump.

If Rod wants that follow-up, keep the existing base images, paths, mirrors/fallbacks and formatting unchanged; test the verification behavior against every release flavor and rebuild the three vendor/OS combinations. Pinned digest values versus the existing fetched `.sha512` check should be an explicit maintainer choice, not an incidental change.

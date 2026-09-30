# Linux release signing key

`linux-release-2026.pub.pem` is the ECDSA P-256 public key for `SHA256SUMS.sig` on the `v<version>-linux` releases. XerahS has the same key built in and refuses a Linux FFmpeg zip whose hash is not in a correctly signed `SHA256SUMS`.

The private key is the `LINUX_SIGNING_KEY` secret of this repo's `release` environment. Only `.github/workflows/linux-release.yml` on `master` uses it.

To rotate: add the new public key here and to XerahS (`FFmpegReleaseVerifier.TrustedKeys`), ship that XerahS, then switch the secret. Keep the old key in XerahS until older releases are no longer needed.

The Windows zips on the `v<version>` releases are not covered by this key.

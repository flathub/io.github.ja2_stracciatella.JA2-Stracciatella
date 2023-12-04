# JA2 Stracciatella Flatpak

A [flatpak][] manifest for [JA2 Stracciatella][ja2].

[flatpak]: https://flatpak.org/
[ja2]: https://github.com/ja2-stracciatella/ja2-stracciatella

## Version bump process

1. Add the new version to `io.github.ja2_stracciatella.JA2-Stracciatella.appdata.xml` in the `releases` element.
2. Update the source URL and its associated sha256 checksum in the `ja2-stracciatella` module.
3. Bump dependent modules when required, by updating the source URL for dependency modules (`sol2`, `fltk`, `string_theory`, etc.).
4. Update Cargo dependencies:

    1. Clone JA2 and switch to the tag corresponding to the version.
    2. Get the [flatpak builder tools](https://github.com/flatpak/flatpak-builder-tools/tree/master/cargo).
    2. Run `python3 flatpak-cargo-generator.py ${JA2_CLONE}/rust/Cargo.lock -o cargo-sources.json`

5. Commit everything into a new branch and make a merge request.


# Split Installer ZIP Artifacts

The installer binaries are stored as ZIP files split into 45 MB parts so they can
be tracked in Git without exceeding GitHub's recommended 50 MB per-file size.

Each ZIP requires every part in its folder. Concatenate the parts first, then
extract the reconstructed ZIP.

## Extract

From the repository root:

```sh
cat artifacts/Obsidian-1.12.7.zip.parts/Obsidian-1.12.7.zip.part-* > Obsidian-1.12.7.zip
cat artifacts/Ritt-1.6.0.zip.parts/Ritt-1.6.0.zip.part-* > Ritt-1.6.0.zip

unzip Obsidian-1.12.7.zip
unzip Ritt-1.6.0.zip
```

## Verify

```sh
shasum -a 256 Obsidian-1.12.7.zip Ritt-1.6.0.zip
shasum -a 256 Obsidian-1.12.7.exe Ritt-1.6.0.msi
```

Expected checksums:

```text
004fd0b63e631445c4ee0ceb07cc8c60213ec6025b0292905acfc945f87503fd  Obsidian-1.12.7.zip
a42dab58b54a5fcc8271148b2ab3a8ae176c34ebb21d97e6c6b1dde9b0a8399e  Ritt-1.6.0.zip
f35d2a35061098400a3fafc1bfd38d8bd33f1ad76df8b78b62ccdf20b0a30d26  Obsidian-1.12.7.exe
65ac5a58386a77cca9ac045204adac1fd08daf9cf43ed3ee07767a5d08df1940  Ritt-1.6.0.msi
```

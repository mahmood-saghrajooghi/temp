# Installer Artifacts

The installer binaries are split into parts so they can be stored in Git without
exceeding GitHub's 100 MB per-file limit.

## Reassemble

From the repository root:

```sh
cat artifacts/Obsidian-1.12.7.exe.parts/part-* > Obsidian-1.12.7.exe
cat artifacts/Ritt-1.6.0.msi.parts/part-* > Ritt-1.6.0.msi
```

## Verify

```sh
shasum -a 256 Obsidian-1.12.7.exe Ritt-1.6.0.msi
```

Expected checksums:

```text
f35d2a35061098400a3fafc1bfd38d8bd33f1ad76df8b78b62ccdf20b0a30d26  Obsidian-1.12.7.exe
65ac5a58386a77cca9ac045204adac1fd08daf9cf43ed3ee07767a5d08df1940  Ritt-1.6.0.msi
```

# STARSEED media export

`manifest.json` lists the exported files by relative path, size, SHA-256, and media kind. `media/` holds only images and playback video referenced by the static viewer indexes. `spine/` holds selectable Spine sets, each with its skeleton, atlas, and all atlas pages in one directory. Identical complete sets may share a canonical directory.

Keep exported bytes unchanged when committing. `.gitattributes` disables Git text conversion so the atlas text bytes match the manifest and the original atlas page names remain valid. This repository contains no database or local source paths.

`3d/` contains the 3D character catalog and runtime assets. Its separate `export-manifest.json` records the SHA-256 and byte count of every 3D file. Character manifests, physics and lighting metadata remain plain JSON; models and animation clips use deterministic gzip (`.json.gz`). Texture paths stay relative to each costume. The viewer decompresses JSON on demand in the browser. Local extraction provenance and source paths are omitted.

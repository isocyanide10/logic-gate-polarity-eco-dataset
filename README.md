# Rotated Logic-Gate Panels and Acyclic Connection Graphs

Original synthetic dataset, version `20260919-logic-eco-v3`.

This dataset contains 2,200 independently constructed acyclic digital-logic graphs and grayscale gate-symbol panels. It supports research on visual gate interpretation and constrained Boolean engineering-change programs. It is not photographed hardware, scanned handwriting, laboratory measurements or an imported benchmark.

## Download

Download **dataset_raw.zip** from this repository's **Releases** section. Release tag: `v20260919-3`.

The ZIP is approximately 69 MB. Verify it against `SHA256SUMS.txt` before use. GitHub's automatically generated source-code ZIP is not the dataset asset.

## Data

Each graph has four or five Boolean primary inputs, eight to sixteen two-input gates and three designated outputs. The six conventional gate types are AND, OR, XOR, NAND, NOR and XNOR. Symbols are procedurally rendered with varying orientation, curvature, aspect ratio, shear, stroke appearance and rasterization. No fonts or third-party image assets are redistributed.

Connectivity is supplied explicitly. Primary input `i` is node `i`; gate `g` is node `n_inputs + g`. `fanins[g]` lists the two earlier input nodes. Pixel intensities are unitless integers from 0 (black) to 255 (white). Crop rectangles are `[left,top,right,bottom]` in pixels, with exclusive right and bottom bounds.

## Archive Contents

| File | Purpose |
|---|---|
| `untyped_topologies.jsonl` | 2,200 graph records with `source_id`, `n_inputs`, `fanins` and `outputs`; no gate or repair labels. |
| `panels/*.png` | One original grayscale symbol panel per graph. |
| `panel_manifest.json` | Graph-to-image joins, image-byte SHA-256 hashes and gate crop boxes; no target labels. |
| `SOURCE_RECORD.json` | Original construction provenance, version and generator/renderer hashes. Its unpublished-URL field records the state when the archive was built, before repository publication. |
| `FILE_CHECKSUMS.json` | Hashes of all other archive files, excluding the checksum file itself. |
| `DATASET_DESCRIPTION.md` | Detailed dataset card, construction process, conventions and limitations as frozen at archive creation. |
| `ATTRIBUTION.md` | Creator credit and explanation of original-data provenance. |
| `LICENSE-DATA.txt` | CC BY 4.0 licensing notice and official legal-text link. |

The files at repository root provide the current card, attribution, licensing notice and the ZIP checksum. Private benchmark keys, evaluation answers, creator preparation scripts and predictions are intentionally not included.

## Construction and Benchmark Use

Random acyclic graphs are pruned to ancestors of their outputs and exact duplicate topologies are removed. Creator-side Boolean simulation assigns gate types and constructs observable repairs with at most three output-polarity toggles. Labels are calculated, not supplied by a language model. Code and documentation were AI-assisted; the raster images are drawn by a procedural renderer, not an image-generation model.

The associated challenge preparation uses 1,800 training circuits and 400 evaluation circuits. Public training labels are released through that challenge; this raw repository itself contains unlabeled graphs and images. It is not a hidden-answer archive or a complete standalone supervised-training release.

This repository is the publication of an original dataset, not a mirror of LogicBench or another external circuit corpus. References to related research do not identify an alternative source of these examples.

## License and Attribution

**Creative Commons Attribution 4.0 International (CC BY 4.0)**, offered by the creator for the original dataset files.

Credit: Nirma ([isocyanide10](https://github.com/isocyanide10)), *Rotated Logic-Gate Panels and Acyclic Connection Graphs*, version `20260919-logic-eco-v3`, 2026.

[Official license terms](https://creativecommons.org/licenses/by/4.0/legalcode.en). Attribute the creator, title and version, include the license link, and indicate modifications. No endorsement or warranty is implied.

## Limitations

The vocabulary is small and synthetic. These data do not establish performance on real schematics, physical boards, sequential or analog circuits, timing hazards or safety-critical engineering. The repository does not certify challenge originality, leaderboard stability or acceptance by any evaluation platform.

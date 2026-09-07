# Locked Geometry Analysis

Authoritative local source: `sentinel_banner_longer_separate_mesh_v3.glb`.

## Findings

- Main body mesh: 72,826 vertices / 36,298 faces.
- `banner_cloth`: 10 vertices / 16 faces, separate geometry/node as required.
- The body is voxel/hard-surface style and consists of many disconnected quad-like islands (18,264 connected components). This makes connected-component material assignment unsuitable for semantic texturing.
- Earlier XYZ-position face masking is rejected because it creates visibly incorrect color regions across the face/armor.

## Final texturing strategy

Because semantic body parts are not separated into useful connected components, texture work must be done through UV/material painting against the locked geometry, not by broad coordinate masks. The body geometry remains unchanged. The banner remains a separate mesh and will receive its own UV/decal treatment.

## Locked rules

1. No body reshape.
2. Preserve scene transforms.
3. Preserve `banner_cloth` as a separate node.
4. Sentinel and Reaper use identical geometry and UV layout.
5. Reaper is derived by palette/material treatment only.

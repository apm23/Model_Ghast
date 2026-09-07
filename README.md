# Model_Ghast

Workspace for the Happy Ghast Sentinel/Reaper model rebuild.

## Locked geometry baseline

The current authoritative local geometry is `sentinel_banner_longer_separate_mesh_v3.glb`.

Rules:
- Do not reshape the body unless a specific geometry revision is justified.
- `banner_cloth` must remain a separate geometry/node for independent runtime flutter animation.
- Sentinel and Reaper share the exact same geometry.
- Sentinel/Reaper differ only by materials/textures/emissive/banner treatment.
- Banner horned-skull artwork is texture/decal work, not relief geometry.

## Workflow

1. Preserve locked geometry.
2. Build correct UV/material segmentation based on actual connected mesh parts, not raw XYZ face masks.
3. Produce Sentinel material/texture set.
4. Derive Reaper from the same geometry and UV layout.
5. Validate scene hierarchy, transforms, bounds, material slots, and separate banner node.
6. Export final GLB assets and integration-ready manifest.

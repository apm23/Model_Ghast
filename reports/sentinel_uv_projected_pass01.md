# Sentinel UV Projected Pass 01

Status: REVIEW PASS, not final.

## Locked source
- `sentinel_banner_longer_separate_mesh_v3.glb`
- Body geometry shape remains locked.
- `banner_cloth` remains a separate node for future flutter animation.

## Method
The rejected XYZ material-mask approach has been removed from the pipeline. This pass uses the existing Sentinel 4-view references (`front/back/left/right`) as projective textures.

Each body triangle is assigned to the most appropriate orthographic view from its face normal, then receives UV coordinates projected into the corresponding reference image. This changes only material/UV organization; triangle positions are not moved.

## Face assignment
- Front: 22,959 faces
- Back: 4,613 faces
- Left: 4,404 faces
- Right: 4,322 faces

## Banner
The banner remains a dedicated `banner_cloth` geometry/node and receives its own side-view projective UV/material. Geometry is unchanged.

## Review decision
This is deliberately not marked final yet. Next pass must visually inspect orientation, crop alignment, seams, banner projection, and front/back/left/right mapping. If any projection is mirrored or offset, fix the UV mapping/crops only; do not alter the locked body shape.

No image generation is used in this pass.

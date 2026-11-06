# Models, costs and capabilities

The tool schema returned by the current connection is the request contract; this reference does not prove which features are deployed. When the user explicitly specifies a model, keep that choice; if the schema rejects the input, explain the limitation instead of quietly switching to a default.

## Choosing a model

- P2: more credits than H/P1. With the P series, P2 is the default and can be suggested first for low-poly or topology needs; quote each option separately and never write zero for an unestimated cost.
- P1: fewer credits and faster; use it only when the user explicitly specifies or selects it. Do not rule it out because of the platform name.
- H: keep it available when its capabilities are needed. When no model is specified, check the service routing first; never present a wrapper default as the official API default.
- The full ID or alias of an explicit model, face count, quad and texture parameters each follow the current tool schema. Do not invent fixed price multiples, and never silently change models or raise costs.

## Retained workflows (discovered at runtime; not all claimed as deployed)

- Text, image and multiview to 3D; image generation, multiview preparation, image to splat; uploads and model import.
- Texturing, decimation/retopology, segmentation, semantic segmentation, completion, local editing, standalone smart UV.
- rig_check, rig, animate, convert; balance, task list/wait/status, usage.
- Do not declare a capability retired just because it is missing. Specific models that are officially retired cannot be called; migration suggestions need user confirmation, and never submit a paid replacement model automatically.

## Parameter interplay

Fast texturing must check the compatible texture version and fields (do not mix generation's texture_version with standalone texturing's model). Rig passes the model explicitly by body type: biped `v3.0` (`v3.0-20260909`); animals (quadruped, hexapod, octopod, avian, serpentine, aquatic) `v2.5` (`v2.5-20260210`, the officially designated animal skeleton). The API's own default is `v1.0-20240301`, which only supports bipeds; when model is omitted, the MCP fills in v3.0 for every body type, so do not rely on defaults. `preset:biped:*` only pairs with v1.0; v2.5/v3.0 use generic or body-type presets. A rig_check task_id cannot be used as the original model input.

Retopology smart_uv and standalone UV are different operations; do not create a duplicate paid UV task for the same need by default. Static prechecks cover the whole planned chain; conditions that cannot be determined before generation must be checked before entering the next paid stage.

Sources: the project review plan (2026-10-27) and the connection's current tools/list. The production deployment and the latest prices must be checked during authorized host acceptance; this package bundles no price or model enums, so a review snapshot is never passed off as a live contract.

# sa-planning

South Australia planning and land layers from Data.SA (Department for Housing and Urban Development, CC BY 4.0): Planning
and Design Code zones and overlays, Land Use Generalised 2025, building height limits, and the building-rule areas (energy
climate zones and concession areas, bushfire protection, earthquake hazard, corrosion), as GeoParquet and vector tiles.
Checked monthly and rebuilt when a source changes; published to Hugging Face
([dataset](https://huggingface.co/datasets/alreadyopen/sa-planning) for Parquet,
[bucket](https://huggingface.co/buckets/alreadyopen/sa-planning) for the PMTiles browsers read) and mirrored to
[Kaggle](https://www.kaggle.com/datasets/helenkwok/sa-planning). Built from
[pipeline-template](https://github.com/AlreadyOpen/pipeline-template). Every feature and field is kept; see `hf/README.md`.

    python3 bake.py [layer ...]   # data/out/: GeoParquet + PMTiles + index.json (needs tippecanoe 2.79); REBAKE=1 bakes unchanged sources
    python3 publish.py            # gate, then Hugging Face (HF_TOKEN)
    python3 check.py              # data-free checks (CI)

The bake fails unless zoom 14 of each tile set holds every feature of its source.

Code: Apache-2.0. Data: CC BY 4.0 (Government of South Australia), see `sources.json`.

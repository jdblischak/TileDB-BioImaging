<a href="https://tiledb.com"><img src="https://github.com/TileDB-Inc/TileDB/raw/dev/doc/source/_static/tiledb-logo_color_no_margin_@4x.png" alt="TileDB logo" width="400"></a>

[![TileDB-BioImaging CI](https://github.com/TileDB-Inc/TileDB-BioImaging/actions/workflows/ci.yml/badge.svg)](https://github.com/TileDB-Inc/TileDB-BioImaging/actions/workflows/ci.yml)
![Coverage Badge](https://img.shields.io/endpoint?url=https://gist.githubusercontent.com/ktsitsi/32d48185733a4e7375e80e3e35fab452/raw/gist_bioimg.json)

# TileDB-BioImaging

Python package for:
- converting images stored in popular Biomedical Imaging formats to groups of TileDB arrays (& vice versa)
- exposing an expressive and efficient API (powered by TileDB) for querying such data.

**Note**: this project is in pretty early stage and under heavy development.
Breaking changes to the underlying data format and the API are to be expected.

## Features

### Ingestion to TileDB Groups of Arrays
    - OME-Zarr
    - OME-Tiff
    - Open-Slide

### Ingestion from TileDB Groups of Arrays to:
    - OME-Zarr (Coming soon)
    - OME-Tiff (Coming soon)


## Quick Installation

- from source by cloning the [Git](https://github.com/TileDB-Inc/TileDB-BioImaging) repository:

      git clone https://github.com/TileDB-Inc/TileDB-BioImaging.git
      cd TileDB-BioImaging

      # If you use zsh replace .[full] with .\[full\]
      pip install -e .[full]

- with pip from git:

      pip install git+https://github.com/TileDB-Inc/TileDB-BioImaging.git@main

## Examples
How to convert imaging data from standard biomedical formats to group of TileDB arrays.

### OME-Zarr to TileDB Group of Arrays
```python
from tiledb.bioimg.converters.ome_zarr import OMEZarrConverter
cnv = OMEZarrConverter()
cnv.convert_image("path_to_ome_zarr_image", "tiledb_array_group_path")
```

### OME-Tiff to TileDB Group of Arrays
```python
from tiledb.bioimg.converters.ome_tiff import OMETiffConverter
cnv = OMETiffConverter()
cnv.convert_image("path_to_ome_tiff_image", "tiledb_array_group_path")
```

### Open Slide to TileDB Group of Arrays
```python
from tiledb.bioimg.converters.openslide import OpenSlideConverter
cnv = OpenSlideConverter()
cnv.convert_image("path_to_open_slide_image", "tiledb_array_group_path")
```

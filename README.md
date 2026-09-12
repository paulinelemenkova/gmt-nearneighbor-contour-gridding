# GMT NearNeighbor Grid — Nearest-Neighbour Gridding and Contour Maps

GMT (Generic Mapping Tools) shell scripts that grid scattered XYZ bathymetry point data into continuous surfaces using the nearneighbor algorithm and map the result as contour maps. nearneighbor is a local interpolation method that assigns each node a weighted average of the nearest points found within a search radius and sectors, leaving nodes empty where no data are present. The examples cover the Kuril-Kamchatka and Mariana Trenches and support figures in the author's marine-geophysical and cartographic publications.

## What the scripts do

- inspect the XYZ data range (gmtinfo)
- convert the ASCII XYZ table to binary for speed (gmt convert)
- grid the points with a nearest-neighbour search radius and sectors (nearneighbor -S -I)
- contour the resulting grid (grdcontour)
- add coastlines, frame, scale bar and directional rose (pscoast, psbasemap)
- add annotations (pstext) and the GMT logo (logo)
- export to raster (psconvert) at high resolution

Nearest-neighbour gridding is a local method: unlike a global spline it produces no output where the neighbourhood contains no data, so genuine data gaps remain visible.

## Data source

Scattered XYZ bathymetry exported from a global grid (e.g. TOPEX/UCSD, 1-arc-minute). Input as ASCII .xyz tables.

## Files

- GMT-19-script-JM-NN-KKT.sh: Kuril-Kamchatka Trench
- GMT-19-script-JM-NN-MT.sh: Mariana Trench

## Requirements

- GMT 6.x (Generic Mapping Tools): https://www.generic-mapping-tools.org
- A POSIX shell (bash/sh)
- The relevant XYZ point table(s) available locally

## Usage

Place the required XYZ table in the working directory, adjust the -I resolution and -S search radius at the top of the chosen script, then run:

    bash GMT-19-script-JM-NN-MT.sh

The script writes a PostScript file and converts it to a raster image (JPG/PNG) via psconvert.

## Author and citation

Polina Lemenkova
ORCID: https://orcid.org/0000-0002-5759-1089

These scripts support figures in the author's marine-geophysical and cartographic papers; please cite the specific article a given figure appears in. The full publication list is available via the ORCID record above.

## License

See the LICENSE file in this repository.

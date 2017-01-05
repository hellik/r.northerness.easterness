# r.northerness.easterness
r.northerness.easterness - Calculation of northerness, easterness and the interaction between northerness and slope - GRASS GIS addon

NAME
r.northerness.easterness - Calculation of northerness, easterness and the interaction between northerness and slope

KEYWORDS
raster, terrain, aspect, slope, sun

SYNOPSIS
r.northerness.easterness
r.northerness.easterness --help
r.northerness.easterness elevation=name [--help] [--verbose] [--quiet] [--ui]
Flags:

--help
    Print usage summary
--verbose
    Verbose module output
--quiet
    Quiet module output
--ui
    Force launching GUI dialog

Parameters:

elevation=name [required]
    Name of elevation raster map

DESCRIPTION
r.northerness.easterness calculates northerness, easterness and the interaction between northerness and slope (northerness*slope). The user must specify the input elevation raster map.

NOTES
As aspect is a circular land-surface parameter, in ecology a sine or cosine transformation is often used to obtain a continuous gradient, stressing the north-south or east-west gradient (northness or eastness).

The GRASS GIS default aspect angles (cartesian) are converted to compass angles.

Calculated raster maps are:

    northerness: cos(aspect)
    easterness: sin(aspect)
    interaction between northerness and slope: northerness*slope

The color of these raster maps are set to grey.
EXAMPLE

  # align region to DEM and habitat vector
  g.region -a raster=DEM align=DEM

  # run r.northerness.easterness
  r.northerness.easterness elevation=DEM
 

SEE ALSO
r.mapcalc, r.slope.aspect

REFERENCES
Olaya, V. 2009. Basic Land-Surface Parameters. In: Hengl, T. & Reuter, H.I. (eds.) 2009. Geomorphometry. Concepts, Software, Applications. Developments in Soil Science, Volume 33. Elsevier.

AUTHOR
Helmut Kudrnovsky 

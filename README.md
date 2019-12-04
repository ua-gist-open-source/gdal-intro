# GDAL and OGR Intro
## Assignment

### Background

GDAL (http://www.gdal.org) is a very powerful library and command utility used to read, write, and transform raster and 
vector geospatial data. GDAL's sister project, OGR, is a library and set of utilities that reads, writes, and transforms
vector data. GDAL is an open source project released under the MIT license, allowing re-purposing for commercial use. As 
such, GDAL is used in both open source and commercial projects (e.g., ESRI's suite) for handling raster data.

As an open source project with lots of configuration options, including the ability to link proprietary libraries for
proprietary data formats, installation and configuration can be tricky so in this class we will use a docker container
which has pre-installed the libraries we need. This simplifies use in that it will run the same on a mac, windows, or linux,
but will require a bit more on the command line in order to access the right docker image, mount a volume, and of course 
run the command.

Reference:
- [GDAL Homepage](https://gdal.org/)
- [GDAL Wikipedia](https://en.wikipedia.org/wiki/GDAL)

## Deliverables
- `answers-1.md` 
- `quickstart-results-screenshot.png`
- `answers-2.md`

## Objective: Explore gdal and ogr tools

## Assignment: Part 1 (GDAL)
As you work through this assignment, compile your answers in a file named `answers.md` in a new branch on this repo named
`solution`. When you have completed the assignment, submit a `Pull Request` to merge with `master`. _Do not merge the branch yourself._

I would like you to peruse the list of GDAL programs on https://gdal.org/programs/index.html#raster-programs as well 
as the OGR programs on https://gdal.org/programs/ogrinfo.html/. Read the `Synopsis`, `Description`, and `Example` of each of 
the programs in the lists. 

### 1. From the GDAL and OGR Program List, find 8 programs, describe them, and compare them with other tools that perform similar functions that you are already familiar with. Add this to `answers-1.md`

## Assignment: Part 2 (GDAL Tutorial)

### Download data
We will use the Natural Earth Data for [1:50m Cross-blended Hypsometric Tints](https://www.naturalearthdata.com/downloads/50m-raster-data/50m-cross-blend-hypso/) with Water. It has also been uploaded to d2l. Download this data and extract to a working directory. Make note of this directory.

### Test `gdal`
Open a command window (Windows users, use `cmd`, Mac/linux users use your favorite terminal application) and navigate to the directory where you have stored your unzipped Natural Earth data.

Type `gdalinfo HYP_50M_SR_W.tif` at the prompt. If you have installed `gdal` successfully and are in the same directory as the data you will see output like this:
```

Driver: GTiff/GeoTIFF
Files: HYP_50M_SR_W.tif
Size is 10800, 5400
Coordinate System is:
GEOGCS["WGS 84",
    DATUM["WGS_1984",
        SPHEROID["WGS 84",6378137,298.257223563,
            AUTHORITY["EPSG","7030"]],
        AUTHORITY["EPSG","6326"]],
    PRIMEM["Greenwich",0],
    UNIT["degree",0.0174532925199433],
    AUTHORITY["EPSG","4326"]]
Origin = (-179.999999999999972,90.000000000000000)
Pixel Size = (0.033333333333330,-0.033333333333330)
Metadata:
  AREA_OR_POINT=Area
  TIFFTAG_DATETIME=2014:10:18 09:46:12
  TIFFTAG_RESOLUTIONUNIT=2 (pixels/inch)
  TIFFTAG_SOFTWARE=Adobe Photoshop CC 2014 (Macintosh)
  TIFFTAG_XRESOLUTION=342.85699
  TIFFTAG_YRESOLUTION=342.85699
Image Structure Metadata:
  INTERLEAVE=PIXEL
Corner Coordinates:
Upper Left  (-180.0000000,  90.0000000) (180d 0' 0.00"W, 90d 0' 0.00"N)
Lower Left  (-180.0000000, -90.0000000) (180d 0' 0.00"W, 90d 0' 0.00"S)
Upper Right ( 180.0000000,  90.0000000) (180d 0' 0.00"E, 90d 0' 0.00"N)
Lower Right ( 180.0000000, -90.0000000) (180d 0' 0.00"E, 90d 0' 0.00"S)
Center      (  -0.0000000,   0.0000000) (  0d 0' 0.00"W,  0d 0' 0.00"N)
Band 1 Block=10800x1 Type=Byte, ColorInterp=Red
Band 2 Block=10800x1 Type=Byte, ColorInterp=Green
Band 3 Block=10800x1 Type=Byte, ColorInterp=Blue
(base)
```

### Follow the QuickStart tutorial
Follow the OSGeoLive QuickStart tutorial at https://live.osgeo.org/en/quickstart/gdal_quickstart.html using the Natural Earth Data.

When you have completed the tutorial, obtain a screenshot of your directory listing. Windows users: use `dir`, Linux/Mac users use `ls -l`. Name the screenshot `quickstart-results-screenshot.png`

### Answer the following questions
Answer the following questions and add them to `answers-2.md`:

1) What command is used to reproject rasters?
2) What command is used to create a JPEG from a tiff?
3) What command is used to change the coordinates of a tiff without modifying the image?
4) What command is used to display geospatial metadata of a raster file?
5) What command lists the supported formats?
6) What command is used to mosaic multiple rasters into one?
7) What command is used to create tiles from a large raster?
8) What command is used to transform between vector formats?
9) What command is used to display metadata for a vector file?

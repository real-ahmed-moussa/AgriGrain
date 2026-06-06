# Dataset: UCI Dry Bean Dataset

## Source

Koklu, M., & Ozkan, I. A. (2020). Multiclass Classification of Dry Beans Using Computer Vision and Machine Learning Techniques. *Computers and Electronics in Agriculture*, 174, 105507.  
https://doi.org/10.1016/j.compag.2020.105507

**Download:** https://archive.ics.uci.edu/dataset/602/dry+bean+dataset

## Description

Digital images of 13,611 dry bean grains across seven registered varieties were processed with computer vision to extract 16 geometric shape features per grain. The classification target is grain variety from shape descriptors alone.

## Properties

| Property | Value |
|---|---|
| Observations | 13,611 |
| Features | 16 (all continuous) |
| Classes | 7 (Barbunya, Bombay, Cali, Dermason, Horoz, Seker, Sira) |
| Missing Values | None |
| Expected filename | `DB.csv` |
| Approximate size | ~3 MB |

## Feature Descriptions

| Column | Description |
|---|---|
| `Area` | Area of the bean zone in pixels |
| `Perimeter` | Bean circumference |
| `MajorAxisLength` | Length of the major axis of the equivalent ellipse |
| `MinorAxisLength` | Length of the minor axis of the equivalent ellipse |
| `AspectRation` | MajorAxisLength / MinorAxisLength (sic — original column name) |
| `Eccentricity` | Eccentricity of the equivalent ellipse |
| `ConvexArea` | Area of the smallest convex polygon containing the bean |
| `EquivDiameter` | Diameter of a circle with the same area |
| `Extent` | Ratio of bean pixels to total bounding-box pixels |
| `Solidity` | Area / ConvexArea |
| `roundness` | 4π × Area / Perimeter² (note: lowercase in original file) |
| `Compactness` | √(4π × Area) / Perimeter |
| `ShapeFactor1` | MajorAxisLength / Area |
| `ShapeFactor2` | MinorAxisLength / Area |
| `ShapeFactor3` | Area / MajorAxisLength² |
| `ShapeFactor4` | Area / (MajorAxisLength × MinorAxisLength) |
| `Class` | Grain variety — classification target |

## How to Obtain

1. Download `Dry_Bean_Dataset.xlsx` from the UCI link above.
2. Open the file and export the data sheet as CSV.
3. Rename the file to `DB.csv` and place it in this directory (`data/raw/DB.csv`).

## License

Dataset provided for academic and research use. Cite Koklu & Ozkan (2020) if you use it.

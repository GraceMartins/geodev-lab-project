# Data Note – Urban Heat Island Effect in Port Harcourt City LGA

## Project Question

Which areas in Port Harcourt City Local Government Area experience the highest land surface temperatures, and how does this correlate with vegetation cover?

---

## Dataset 1: Administrative Boundary – Port Harcourt City LGA

- **Source:** GRID3 Nigeria
- **Source link:** https://grid3.org/datasets?country=nigeria
- **Feature count:** 1 polygon (Port Harcourt City LGA)
- **Key columns:** lga_name, state_name, area_km2
- **Geometry type:** Polygon
- **Gaps/missing values:** None observed. Boundary is complete and covers the full LGA.

---

## Dataset 2: Landsat 8 Thermal Imagery (Land Surface Temperature)

- **Source:** USGS Earth Explorer
- **Source link:** https://earthexplorer.usgs.gov/
- **Feature count:** Raster image (1 scene covering Port Harcourt)
- **Key bands used:** Band 10 – Thermal Infrared Sensor (TIRS 1)
- **Raster resolution:** 100 metres (resampled to 30 metres in delivered product) [citation:16][citation:2]
- **Date acquired:** [Insert date from your downloaded scene]
- **Cloud cover:** [Insert % from your search]
- **Gaps/missing values:** Some cloud cover present. No data gaps within the LGA boundary. Thermal band has lower resolution (100m) resampled to 30m [citation:16].

---

## Dataset 3: Landsat 8 Imagery for NDVI (Vegetation Cover)

- **Source:** USGS Earth Explorer
- **Source link:** https://earthexplorer.usgs.gov/
- **Feature count:** Raster image (same scene as thermal)
- **Key bands used:** Band 4 (Red) and Band 5 (Near Infrared) [citation:8][citation:20]
- **Raster resolution:** 30 metres
- **Gaps/missing values:** No missing data within LGA. Cloud cover may affect NDVI calculation in some areas.

---

## Dataset 4: Settlement Extents

- **Source:** GRID3 Nigeria / Columbia University
- **Source link:** https://doi.org/10.7916/z5w9-cn03
- **Feature count:** [Insert number after opening in QGIS]
- **Key columns:** settlement_name, settlement_type, area_km2
- **Geometry type:** Polygon
- **Gaps/missing values:** Some small settlements may not be captured. v4.1 removed hamlets and edge-blocks with zero-building count [citation:1].

---

## Summary of Data Quality

| Dataset | Complete? | Issues |
|---------|-----------|--------|
| Administrative boundary | Yes | None |
| Thermal imagery | Yes | Cloud cover in some areas |
| NDVI imagery | Yes | Cloud cover in some areas |
| Settlement extents | Partial | Some small settlements missing |

---

## How This Data Answers the Question

1. **Administrative boundary** defines the study area (Port Harcourt City LGA)
2. **Thermal imagery** calculates land surface temperature for each pixel
3. **NDVI imagery** calculates vegetation health for each pixel
4. **Settlement extents** identify where people live within the LGA

By overlaying temperature and NDVI, we can identify:
- Areas with high temperature and low vegetation (heat hotspots)
- Areas with low temperature and high vegetation (cool zones)
- How settlement patterns relate to heat distribution

# Data Note – Urban Heat Island Effect in Port Harcourt City LGA

## Project Question

Which areas in Port Harcourt City Local Government Area experience the highest land surface temperatures, and how does this correlate with vegetation cover?

---

## Dataset 1: Administrative Boundary – Port Harcourt City LGA

- **Source:** GRID3 Nigeria
- **Source link:** https://grid3.org/geospatial-data-nigeria
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
- **Raster resolution:** 30 metres
- **Date acquired:** 2025-01-15
- **Cloud cover:** Less than 10%
- **Gaps/missing values:** Some cloud cover present. No data gaps within the LGA boundary. Band 11 is not included in Level-2 products and should not be used.

---

## Dataset 3: Landsat 8 Imagery for NDVI (Vegetation Cover)

- **Source:** USGS Earth Explorer
- **Source link:** https://earthexplorer.usgs.gov/
- **Feature count:** Raster image (same scene as thermal)
- **Key bands used:** Band 4 (Red) and Band 5 (Near Infrared)
- **Raster resolution:** 30 metres
- **Gaps/missing values:** No missing data within LGA. Cloud cover may affect NDVI calculation in some areas.

---

## Dataset 4: Settlement Extents

- **Source:** GRID3 Nigeria / Columbia University
- **Source link:** https://doi.org/10.7916/73v5-mq06
- **Feature count:** 1,247 settlement polygons
- **Key columns:** settlement_name, settlement_type, area_km2
- **Geometry type:** Polygon
- **Gaps/missing values:** Some small settlements may not be captured. Hamlets and edge-blocks with zero-building count were removed in v4.1.

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

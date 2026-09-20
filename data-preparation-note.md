# Data Preparation Note – Urban Heat Island Project

## Project Question

Which areas in Port Harcourt City Local Government Area experience the highest land surface temperatures, and how does this correlate with vegetation cover?

---

## 1. Coordinate Reference System (CRS)

- **CRS chosen:** EPSG:26392 – Minna / Nigeria Mid Belt
- **Why this CRS:** It is the official projected CRS for Nigeria. It uses **metres** as its unit, which is ideal for calculating distances and areas accurately within Port Harcourt City LGA. A geographic CRS such as EPSG:4326 would give measurements in degrees, which is not suitable for spatial analysis.

---

## 2. Reprojection

All layers were reprojected from their original CRS to **EPSG:26392**:

| Layer | Original CRS | New CRS |
|-------|--------------|---------|
| Administrative boundary | EPSG:4326 | EPSG:26392 |
| Settlement extents | EPSG:4326 | EPSG:26392 |
| Landsat thermal band | EPSG:32632 | EPSG:26392 |
| Landsat NDVI bands | EPSG:32632 | EPSG:26392 |

---

## 3. Clipping

All layers were clipped to the **Port Harcourt City LGA boundary** so only data within the study area remains.

| Layer | Clipped? | Result |
|-------|----------|--------|
| Administrative boundary | Yes | Only Port Harcourt City LGA |
| Settlement extents | Yes | Only settlements within LGA |
| Thermal imagery | Yes | Only pixels within LGA |
| NDVI imagery | Yes | Only pixels within LGA |

---

## 4. The Five Quality Checks

### Check 1: Geometry Validity
- **Method:** Vector → Geometry Tools → Check Validity
- **Result:** All polygon geometries are valid. No self-intersections or slivers found.

### Check 2: CRS Consistency
- **Method:** Checked each layer's properties → Information
- **Result:** All layers now use EPSG:26392. CRS is consistent.

### Check 3: Attribute Completeness
- **Method:** Opened attribute tables and checked for NULL values
- **Result:** Some missing values in key columns (e.g., missing name and type fields in settlement extents). Flagged as data gaps.

### Check 4: Spatial Extent
- **Method:** Zoomed to each layer and compared with LGA boundary
- **Result:** All layers cover the full extent of Port Harcourt City LGA.

### Check 5: Duplicate Features
- **Method:** Vector → Geometry Tools → Delete Duplicate Geometries
- **Result:** No duplicate geometries found.

---

## 5. Problems Found and Actions Taken

| Problem | Action Taken |
|---------|--------------|
| Missing attribute values in settlement data | Flagged in this note |
| Some small settlements not captured | Flagged – GRID3 v4.1 removed hamlets |
| Cloud cover in satellite imagery | Chose scene with <10% cloud cover |
| Raster band resolution mismatch (thermal 100m vs optical 30m) | Noted; thermal resampled to 30m in delivered product |

---

## 6. Analysis-Ready Files

All analysis-ready files are saved as a GeoPackage on my local machine:

**File name:** `portharcourt_analysis.gpkg`

Layers included:
- `boundary_phc` – Administrative boundary (clipped)
- `settlements_phc` – Settlement extents (clipped)
- `temperature_phc` – Land surface temperature (clipped)
- `ndvi_phc` – Vegetation index (clipped)

**CRS for all layers:** EPSG:26392 – Minna / Nigeria Mid Belt

**Study area:** Port Harcourt City Local Government Area, Rivers State, Nigeria

---

## Summary

The data is now analysis-ready and prepared for calculating land surface temperature and NDVI to answer the project question.
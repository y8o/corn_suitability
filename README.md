# Corn Suitability Analysis – Missouri

This project uses ArcGIS to conduct a raster-based site suitability analysis to identify ideal locations for corn cultivation in Missouri. The analysis is based on four key factors:

- **Land Use** – Areas appropriate for agriculture
- **Soil Drainage** – Well-drained soils best for corn
- **Slope** – Flat areas are preferred
- **Proximity to Roads** – Close enough for transport, but not too close due to pollution

## Methodology

1. **Data Preparation**
   - Converted vector data to raster (50m resolution)
   - Reclassified input layers to a 1–5 suitability scale

2. **Euclidean Distance**
   - Computed distance to nearest roads
   - Reclassified to favor middle-distance zones

3. **Weighted Overlay**
   - Combined reclassified rasters using the following weights:
     ```
     ("Land Use" * 2 + "Soil" * 3 + "Slope" * 1 + "Road Distance" * 2) / 8
     ```

4. **Output**
   - Final suitability raster with classification: Excellent, Good, Fair, Poor, Unsuitable

## Files

- [`corn-suitability.pdf`](./corn-suitability.pdf): Final report with maps and methodology
- No code available as this was performed entirely within ArcMap Desktop using GUI-based workflows

## Tools Used

- ArcGIS Desktop
- Spatial Analyst Tools
- Raster Calculator

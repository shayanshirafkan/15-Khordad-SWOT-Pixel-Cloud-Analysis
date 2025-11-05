# Dez River SWOT Pixel Cloud Analysis

This repository contains Python scripts to analyze and visualize **SWOT L2 Pixel Cloud data** for the **15 Khordad Dam** (Iran).  

**Important Note:**  
The original SWOT pixel cloud dataset is very large. For convenience, we have **extracted only the region around 15 Khordad Dam** and uploaded this smaller dataset here. You can run the scripts on this reduced dataset or on the full dataset if you have sufficient storage and memory.  

## Files

### 1. `cut_data.py`
- Reads the original large NetCDF pixel cloud file.  
- Filters points within the 15 Khordad Dam bounding box.  
- Saves a reduced dataset as `SWOT_15Khordad_small.nc`.  

### 2. `plot_data.py`
- Loads the reduced NetCDF dataset (`SWOT_15Khordad_small.nc`).  
- Creates two plots:  
  1. All pixel cloud classes labeled by name.  
  2. Open water points (class 4) colored by **height (WSE)**.  
- Adds a basemap using CartoDB Positron.  

### 3. `SWOT_15Khordad_small.nc`
- Reduced pixel cloud data for the 15 Khordad Dam region.  

## Class Mapping
| Class ID | Name |
|----------|------|
| 1 | land |
| 2 | land_near_water |
| 3 | water_near_land |
| 4 | open_water |
| 5 | dark_water |
| 6 | low_coh_water_near_land |
| 7 | open_low_coh_water |

## How to Run

1. If you want to reproduce the reduced dataset from the full file (requires original NetCDF):  
```bash
python cut_data.py

# GeoLife Trajectory Clustering and Analysis

This project processes and clusters GPS trajectory data from the GeoLife dataset using Spark and Python, with techniques like k-d tree partitioning and DBSCAN clustering. It’s designed to efficiently handle large-scale geographic data, identify clusters, and detect patterns in user movement.

## Key Features
- **Data Sampling**: Extracts and samples data from GeoLife `.plt` files.
- **k-d Tree Partitioning**: Divides geographic data using a k-d tree to optimize clustering.
- **DBSCAN Clustering**: Applies DBSCAN to partitioned data for density-based clustering.
- **Border Detection**: Detects border points in clusters for merging across partitions.
- **Visualization**: Generates visualizations of clusters and borders for spatial analysis.

## Setup

### Requirements
- Python (>= 3.7)
- **Libraries**: `pyspark`, `pandas`, `scikit-learn`, `matplotlib`, `geopandas`, `folium`, `networkx`, `scipy`

### Installation
1. Clone this repository and install dependencies:
   ```bash
   git clone https://github.com/yourusername/GeoLife-Trajectory-Clustering.git
   cd GeoLife-Trajectory-Clustering
   pip install -r requirements.txt
   ```
2. Download the [GeoLife dataset](https://www.microsoft.com/en-us/research/project/geolife-building-social-networks-using-human-location-history/) and place it in the `data/` folder.

3. Start a Spark session in your notebook or script:
   ```python
   from pyspark.sql import SparkSession
   spark = SparkSession.builder.appName("GeoLifeData").getOrCreate()
   ```

## Methodology
1. **k-d Tree Partitioning**: Recursively splits data by longitude and latitude to assign partitions.
2. **DBSCAN Clustering**: Clusters each partition, identifies dense regions, and detects border points for merging clusters that span partitions.
3. **Visualization**: Plots clusters and highlights border points.

## Results
This approach efficiently clusters geographic data, allowing visual analysis of dense and sparse trajectory patterns, with emphasis on clusters spanning multiple regions.

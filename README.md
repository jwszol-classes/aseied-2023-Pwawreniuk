# Image Processing Pipeline in Jupyter Notebook on AWS EMR
This is a Python code repository for an image processing pipeline that processes elevation data tiles retrieved from an external source. The pipeline processes the tiles and generates a color-mapped output. This code was developed and tested in a Jupyter Notebook environment on an AWS EMR (Elastic MapReduce) cluster. Here's an overview of the code and how to use it:

## Prerequisites
Before running the code, make sure you have the required dependencies installed. The code uses PySpark, OpenCV (opencv-python), NumPy, and Matplotlib. You can install these dependencies using the following commands:
```
sc.uninstall_package('pip')
sc.install_pypi_package("pip==22.2.2")
sc.install_pypi_package("opencv-python")
sc.install_pypi_package("numpy")
sc.install_pypi_package("matplotlib")
```
## Functions
### Transformation Functions
**transform_geo_to_tile(lat, lon)** - Transforms geographical coordinates into tile coordinates.

**transform_tile_to_geo(x, y)** - Transforms tile coordinates into geographical coordinates.
### Tile Generation
**generate_tiles(lat1, lon1, lat2, lon2)** - Generates a list of URLs for tile retrieval based on specified geographical coordinates.
### Image Processing Functions
**display_output_map(tile_set, x_count, y_count)** - Displays a composite map from a set of tiles.

**calc_height_increase(pixel_data)** - Calculates elevation from pixel data.

**generate_elevation_thresholds(pixel_data)** - Generates elevation thresholds based on pixel data.

**apply_elevation_thresholds(input_array, thresholds)** - Applies elevation thresholds to an input array.

**apply_color_mapping(pixel_data, thresholds)** - Applies color mapping to pixel data.
### File Path Extraction Functions
**extract_x(filepath)** - Extracts the X coordinate from a file path.

**extract_y(filepath)** - Extracts the Y coordinate from a file path.
### Main Pipeline Function
**run_image_processing_pipeline()** - The main pipeline function that orchestrates the entire process. It retrieves tiles, processes them, applies thresholds, generates color mappings, and displays the output.
## Usage
* To use this image processing pipeline in a Jupyter Notebook on an AWS EMR cluster, follow these steps:

* Launch an AWS EMR cluster with the necessary configuration and Spark installed.

* Connect to the EMR cluster using SSH or another method.

* Launch a Jupyter Notebook server on the EMR cluster.

* Create a new Jupyter Notebook or open an existing one.

* Copy and paste the code into a Jupyter Notebook cell.

* Ensure that you have installed the required dependencies as mentioned in the "Prerequisites" section on the EMR cluster.

* Customize the coords variable in the run_image_processing_pipeline() function to specify the geographical coordinates for tile retrieval.

* Run the run_image_processing_pipeline() function within the Jupyter Notebook cell to execute the entire pipeline on the EMR cluster.

* The processed output will be displayed using Matplotlib in the Jupyter Notebook, and a color-mapped image will be saved as 'color_mapped_output.png' on the EMR cluster's storage.

## Results
The result of our program is a map with six zones of average elevation marked on it
![Elevation map](https://github.com/jwszol-classes/aseied-2023-Pwawreniuk/blob/main/output_map.png)
## Note
This code is designed to process elevation data tiles and demonstrate various image processing techniques in a Jupyter Notebook on an AWS EMR cluster. You can further customize and extend it according to your specific requirements.

Enjoy using the image processing pipeline in your Jupyter Notebook on AWS EMR!

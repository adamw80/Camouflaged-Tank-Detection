This repository contains a comprehensive pipeline for image processing and analysis, specifically designed for handling images from a Canon camera, converting them to a more accessible format, and performing various operations to analyze differences between images. This pipeline also includes functionality for calculating distances and mapping locations. *Note that I have retracted parts of the code due to the possibility of possible malicious use.* If you would like to see the full code, please reach out to me. 


# Camouflaged Vehicle Detection and Localization Project

## Project Overview

This project focuses on detecting and localizing camouflaged vehicles in images using advanced computer vision techniques. The workflow involves preprocessing RAW images, detecting vehicles using the YOLOv5 model, extracting metadata, and calculating the positions of detected vehicles relative to the camera using geospatial computations.

### Key Objectives:

1. **Image Preprocessing:**
   - Convert RAW images (.CR2 format) to PNG for further processing.
   
2. **Vehicle Detection:**
   - Detect vehicles in images using the YOLOv5 model and store the detected bounding box coordinates.
   
3. **Metadata Extraction:**
   - Extract camera metadata, such as focal length, tilt, and GPS coordinates, to aid in geolocation computations.

4. **Geospatial Localization:**
   - Calculate the real-world coordinates of detected vehicles using the camera's position, altitude, and other metadata.

5. **Visualization:**
   - Create interactive maps to visualize the positions of detected vehicles relative to the camera location.

## Project Structure

### 1. Image Conversion
- **Convert RAW to PNG:** Convert images from Canon's RAW format (.CR2) to PNG for compatibility with OpenCV and other image processing libraries.

### 2. Image Processing
- **Load and Sort Images:** Load images based on their modification timestamps to identify the oldest and newest images for comparison.
- **Align and Crop Images:** Align images to focus on specific regions and crop for targeted processing.

### 3. Vehicle Detection using YOLOv5
- **Run YOLOv5 Detection:** Use YOLOv5 to detect vehicles in the zoomed images and output bounding box coordinates.
- **Bounding Box Adjustments:** Convert bounding box coordinates from detected images to the original image coordinates.

### 4. Geospatial Calculations
- **Metadata Extraction:** Extract metadata (e.g., focal length, tilt, GPS coordinates) from the camera files using `exiftool`.
- **Geolocation Computation:** Calculate the real-world positions of detected vehicles using the camera's position and orientation data.
- **Distance and Bearing Calculation:** Compute the distance and bearing of detected objects relative to the camera's position.

### 5. Visualization and Mapping
- **Interactive Map Creation:** Create a Folium map with markers representing the positions of detected vehicles and the camera location.
- **Save Map:** Save the generated map as an HTML file for easy sharing and visualization.

## Dependencies

The project requires the following libraries:

- **Image Processing:** `opencv-python`, `PIL`, `rawpy`, `imageio`
- **Geospatial Calculations:** `geopy`, `folium`
- **Machine Learning:** `torch`, `yolov5` (for YOLOv5 model)
- **Metadata Extraction:** `exiftool`
- **Miscellaneous:** `numpy`, `matplotlib`

To install all dependencies, run:
```bash
pip install opencv-python Pillow rawpy imageio geopy folium torch exiftool numpy matplotlib
```

## Usage

1. **Convert Images:**
   Place the RAW images (.CR2 files) in the specified directory and run the conversion function to convert them to PNG format.

2. **Run Vehicle Detection:**
   Execute the YOLOv5 detection script to identify vehicles in the zoomed images.

3. **Extract Metadata:**
   Use the provided function to extract camera metadata such as GPS coordinates, focal length, and bearing.

4. **Calculate Positions:**
   Run the geospatial calculation script to determine the real-world positions of detected vehicles based on the camera's metadata.

5. **Visualize Results:**
   Generate an interactive map showing the locations of detected vehicles and the camera position. Save the map as an HTML file for easy sharing.

## Dataset

The project uses images captured using a Canon camera in RAW format. The dataset includes various images of camouflaged vehicles taken from different angles and distances.

## References

1. YOLOv5 Documentation - [YOLOv5](https://github.com/ultralytics/yolov5)
2. Geopy Documentation - [Geopy](https://geopy.readthedocs.io/)
3. OpenCV Documentation - [OpenCV](https://opencv.org/)
4. EXIFTool Documentation - [EXIFTool](https://exiftool.org/)

## Acknowledgments

This project is developed to enhance the detection and localization of camouflaged vehicles using state-of-the-art computer vision techniques and geospatial analysis. Special thanks to the developers of YOLOv5, Geopy, and EXIFTool for providing robust tools and libraries.

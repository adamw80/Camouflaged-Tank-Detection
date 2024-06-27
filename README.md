This repository contains a comprehensive pipeline for image processing and analysis, specifically designed for handling images from a Canon camera, converting them to a more accessible format, and performing various operations to analyze differences between images. This pipeline also includes functionality for calculating distances and mapping locations. Note that I have retracted parts of the code due to the possibility of possible malicious use. If you would like to see the full code, please reach out to me. 

Features

1. Image Conversion
Convert Canon .CR2 Images to .PNG: This module converts raw images from a Canon camera (with .CR2 format) to .PNG format for easier processing.
2. Image Loading
Load Images by Timestamp: This functionality loads images from a specified folder, sorting them by their modification times to identify the oldest and newest images.
3. Image Analysis
Image Difference Calculation: Utilizes OpenCV and other image processing libraries to analyze and visualize differences between two images.
4. Distance Calculation
Calculate Distance Between Points: Implements mathematical functions to calculate distances between points in the images.
5. Map Integration
Map Locations with Folium: Integrates geolocation data and maps points using the Folium library to provide a visual representation of locations on a map.
Prerequisites

Python 3.x
Required Python Libraries: matplotlib, numpy, opencv-python, rawpy, imageio, PIL, exiftool, math, folium, geopy
Installation

Clone the repository:
sh
Copy code
git clone https://github.com/your-repo/image-processing-pipeline.git
Navigate to the project directory:
sh
Copy code
cd image-processing-pipeline
Install the required dependencies:
sh
Copy code
pip install -r requirements.txt
Usage

Convert Images: Place your .CR2 images in the specified source folder and run the conversion function:
python
Copy code
source_folder = '/path/to/your/images'
convert_images_to_png(source_folder)
Load Images: Load the oldest and newest images from the folder for analysis:
python
Copy code
image_1, image_2 = load_images_by_timestamp(source_folder)
Perform Image Analysis: Use the loaded images to perform further analysis as needed.
Example

python
Copy code
# Specify the source folder
source_folder = '/path/to/your/images'

# Convert images to PNG format
convert_images_to_png(source_folder)

# Load the oldest and newest images
image_1, image_2 = load_images_by_timestamp(source_folder)

# Proceed with your image analysis...
Contributing

Feel free to fork this repository and submit pull requests. For major changes, please open an issue first to discuss what you would like to change.

License

This project is licensed under the MIT License - see the LICENSE file for details.


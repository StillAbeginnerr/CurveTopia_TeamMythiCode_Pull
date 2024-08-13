## Solution for Adobe GenSolve CurveTopia by Team MythiCode Pull

# Geometric Shape Analysis and Symmetry Detection

This repository contains Python scripts for processing and visualizing geometric shapes from CSV data. The main functionalities include shape regularization, symmetry detection, curve interpolation, and handling occlusions. Below is a detailed breakdown of the key functions and their roles in the script.

## Table of Contents

1. [Importing Libraries](#importing-libraries)
2. [Convert Polylines to SVG and PNG](#convert-polylines-to-svg-and-png)
3. [Check if Points Form a Straight Line](#check-if-points-form-a-straight-line)
4. [Regularize Open Curves](#regularize-open-curves)
5. [Identify Shapes from Contours](#identify-shapes-from-contours)
6. [Plot Curves on a 2D Plane](#plot-curves-on-a-2d-plane)
7. [Regularize Closed Curves](#regularize-closed-curves)
8. [Process and Regularize All Curves](#process-and-regularize-all-curves)
9. [Generate a Regularized Image](#generate-a-regularized-image)
10. [Plot Original and Regularized Images Side by Side](#plot-original-and-regularized-images-side-by-side)
11. [Symmetry Identification Functions](#symmetry-identification-functions)
12. [Drawing Dashed Lines for Symmetry Visualization](#drawing-dashed-lines-for-symmetry-visualization)
13. [Symmetry Checking and Visualization](#symmetry-checking-and-visualization)
14. [Occlusion Handling with Model Fitting](#occlusion-handling-with-model-fitting)
15. [Processing and Saving Completed Curves](#processing-and-saving-completed-curves)

## Importing Libraries

**Purpose**: To import essential Python libraries that provide the functionality needed for data processing, image manipulation, and shape analysis.

**Libraries Imported**:
- **NumPy (`np`)**: For numerical operations and array manipulation.
- **svgwrite**: For creating SVG files to represent geometric shapes.
- **cairosvg**: For converting SVG files to PNG images.
- **scikit-learn (`LinearRegression`)**: For fitting lines to data points and detecting straight lines.
- **scipy (`savgol_filter`)**: For smoothing data points using the Savitzky-Golay filter.
- **PIL (Pillow)**: For image processing.
- **OpenCV (`cv2`)**: For advanced image processing, including contour detection.
- **Matplotlib (`plt`)**: For plotting and visualizing data.

## Convert Polylines to SVG and PNG

**Purpose**: Converts a list of polyline paths into an SVG file and then into a PNG image using `cairosvg`.

**Key Steps**:
1. **Calculate Canvas Size**: Determine the maximum width and height based on the coordinates.
2. **Create SVG Drawing**: Draw each polyline path on the SVG canvas.
3. **Handle Colors**: Assign colors to each path.
4. **Save SVG and Convert to PNG**: Save the SVG and convert it to a PNG image.

## Check if Points Form a Straight Line

**Purpose**: Determines whether a series of points form a straight line by fitting a line to the points using linear regression.

**Key Steps**:
1. **Fit a Line**: Use `LinearRegression` to fit a line to the points.
2. **Calculate Deviations**: Measure the deviation of each point from the fitted line.
3. **Check Tolerance**: Determine if all deviations are within a specified tolerance to confirm a straight line.

## Regularize Open Curves

**Purpose**: Processes open curves by smoothing them and determining if they are straight lines or irregular curves.

**Key Steps**:
1. **Extract Points**: Retrieve all points forming the open curves.
2. **Smooth the Curve**: Apply the Savitzky-Golay filter to smooth the curve.
3. **Check for Straight Lines**: Use the `check_straight_line` function to identify straight lines.
4. **Classify and Store**: Classify the curve and store it for further processing.

## Identify Shapes from Contours

**Purpose**: Identifies and classifies geometric shapes based on contours detected in the image.

**Key Steps**:
1. **Approximate Contour**: Simplify the contour using `cv2.approxPolyDP`.
2. **Calculate Area and Perimeter**: Compute the area and perimeter of the contour.
3. **Calculate Centroid**: Determine the centroid of the shape.
4. **Classify Shape**: Identify the shape (e.g., triangle, rectangle, circle) based on contour properties.
5. **Return Shape Information**: Provide details about the detected shape.

## Plot Curves on a 2D Plane

**Purpose**: Plots a given curve (a set of points) on a 2D plane using Matplotlib.

**Key Steps**:
1. **Create a Plot**: Initialize a Matplotlib figure and axis.
2. **Plot Points**: Plot the points of the curve.
3. **Set Axis Limits**: Adjust the plot limits to fit the points.
4. **Hide Axes**: Hide the axes for a clean visualization.

## Regularize Closed Curves

**Purpose**: Regularizes closed curves by identifying the shapes they form and adjusting them to standard geometric forms.

**Key Steps**:
1. **Extract Points**: Retrieve points forming the closed curves.
2. **Adjust Points**: Apply margin adjustments to the points.
3. **Convert Plot to Image**: Convert the plot into a NumPy array and process it as an image.
4. **Find Contours**: Detect contours using OpenCV.
5. **Identify and Classify Shapes**: Classify shapes using the `identify_shapes` function.
6. **Handle Irregular Shapes**: Classify non-standard shapes as "Irregular."

## Process and Regularize All Curves

**Purpose**: Integrates the regularization of both open and closed curves, producing a unified set of standardized shapes.

**Key Steps**:
1. **Group Segments into Curves**: Group segments from the CSV into open and closed curves.
2. **Regularize Closed Curves**: Process closed curves using `regularize_closed_curves`.
3. **Regularize Open Curves**: Process open curves using `regularize_open_curves`.
4. **Combine Results**: Combine the results into a single list of plots.

## Generate a Regularized Image

**Purpose**: Creates a visual representation of all regularized shapes and saves the result as a PNG image.

**Key Steps**:
1. **Create Figure and Axis**: Set up a Matplotlib figure and axis.
2. **Plot Each Shape**: Draw each regularized shape on the plot.
3. **Set Aspect Ratio and Save**: Adjust the aspect ratio and save the image.
4. **Return Image Path**: Save the image and return its path.

## Plot Original and Regularized Images Side by Side

**Purpose**: Visually compares the original curves with their regularized counterparts.

**Key Steps**:
1. **Extract Base Name**: Extract the file name for labeling.
2. **Read Original Paths**: Load the original curves from the CSV.
3. **Regularize Curves**: Apply regularization to the curves.
4. **Create Side-by-Side Plot**: Display the original and regularized images side by side.

## Symmetry Identification Functions

### Check Pairwise Vertex Symmetry

**Purpose**: Checks if a polygon's vertices have symmetry by reflecting each vertex pair across lines defined by other vertex pairs.

**Key Steps**:
1. **Reflect Points**: Reflect each vertex across the line formed by another vertex pair.
2. **Check Symmetry**: Verify if reflected points match existing vertices.
3. **Record Symmetry Lines**: Store valid symmetry lines.

### Check Perpendicular Bisector Symmetry

**Purpose**: Checks if a shape has symmetry along the perpendicular bisectors of its edges.

**Key Steps**:
1. **Calculate Midpoints and Slopes**: Determine midpoints and slopes for edges.
2. **Reflect Points**: Reflect points across bisectors.
3. **Check Symmetry**: Confirm symmetry by comparing reflected and original points.
4. **Record Symmetry Lines**: Store detected symmetry lines.

## Drawing Dashed Lines for Symmetry Visualization

**Purpose**: Draws dashed lines on an image to visualize the lines of symmetry.

**Key Steps**:
1. **Calculate Line Length**: Determine the total length of the symmetry line.
2. **Determine Number of Dashes**: Calculate the number of dashes required.
3. **Draw Dashes**: Use OpenCV to draw dashed lines.

## Symmetry Checking and Visualization

**Purpose**: Integrates symmetry detection and draws the identified lines of symmetry on regularized shapes.

**Key Steps**:
1. **Regularize Shapes**: Regularize the shapes from the CSV file.
2. **Load Regularized Image**: Load the processed image for symmetry analysis.
3. **Identify and Classify Shapes**: Detect shapes and identify symmetry.
4. **Draw Symmetry Lines**: Visualize the symmetry lines on the image.
5. **Display Results**: Show the original and symmetry-annotated images side by side.

## Occlusion Handling with Model Fitting

### Remove Coincident Points

**Purpose**: Removes points that coincide with points on a curve boundary to clean the data.

**Key Steps**:
1. **Compare Points**: Check if each point coincides with boundary points.
2. **Filter Points**: Retain non-coincident points.

### Interpolate and Extrapolate Curves

**Interpolate Curve**
- **Purpose**: Generates additional points along a curve for smoother representation.
- **Key Steps**:
  1. **Spline Fitting**: Fit a spline to the points.
  2. **Generate Points**: Create new points along the spline.

**Extrapolate Curve**
- **Purpose**: Extends a curve beyond its original endpoints.
- **Key Steps**:
  1. **Extend Spline**: Extrapolate points beyond the original curve.

## Processing and Saving Completed Curves

**Purpose**: Processes closed curves, fits geometric models (like circles and ellipses), and saves the processed data to a CSV file.

**Key Steps**:
1. **Calculate Residuals**: Compare the fit of different models to data points.
2. **Fit Geometric Models**: Fit circles and ellipses to the data.
3. **Determine Best Fit**: Choose the model with the smallest residuals.
4. **Remove Coincident Points**: Clean the data by removing points that overlap with the model.
5. **Save Results**: Write the processed data to a new CSV file.

## How to Run the Jupyter Notebook

To explore and execute the code in this repository, you can run the Jupyter Notebook (`.ipynb` file) in a local or cloud-based environment. If you have Jupyter installed locally, simply open your terminal, navigate to the directory containing the `.ipynb` file, and run `jupyter notebook`. This will open the Jupyter interface in your web browser, where you can select and open the notebook file. Alternatively, you can use cloud platforms like Google Colab or Kaggle, which allow you to upload and run Jupyter Notebooks without any setup. After opening the notebook, you can run each code cell sequentially by clicking on the cell and pressing `Shift + Enter`. This will allow you to follow the shape processing, regularization, and symmetry detection steps interactively.


---

Feel free to explore the code and contribute to this project. If you have any questions or suggestions, please open an issue or submit a pull request.

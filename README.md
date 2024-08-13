## Solution for Adobe GenSolve CurveTopia by Team MythiCode Pull

## Demo Video

![image](https://github.com/user-attachments/assets/0699c2bc-c807-446a-9ec3-d33b68f343af)
![image](https://github.com/user-attachments/assets/ec4bf2f3-0d98-4ffd-bc2b-bd70c05e2f65)

## Table of Contents 📃
- [Approach](#approach)
- [How to Run](#how-to-run)
- [Detailed Code Understanding](#detailed-code-understanding)
- [Future Vision](#future-vision)
- [Contributing](#contributing)

## Approach 📌

We tried and tested multiple solutions through trial and error, combining multiple technologies:
- R-CNN for Shapes Detection
- Pure OpenCV Countours based approach
- RDP Algorithm for shape simplification as smoothing
- Image Segmentation for Shape Detections

However, the best solution as highlighted in [99_Accurate_Solution.ipynb](https://github.com/thejediboySHASHANK/CurveTopia_MythiCode_Pull/blob/main/99_Accurate_Solution.ipynb),
was achieved through a meticulate combination of all the above listed trials, errors and optimizations on top of that.

For us, accuracy was the single-most important metric from Day-0, and we put all our efforts into that with a laser sharp focus.
We wanted to create a nice UI, or a convert it into a SaaS, however we aligned them with out future vision and came up with the magical 99% accurate solution.

- Dataset Import: Automated CSV file import and preprocessing for geometric data.
- Curve Grouping: Classified segments into open and closed curves based on connectivity.
- Shape Identification: Using OpenCV + Basic Geometric shapes formulas (Areas, Perimeter, radius, etc) to approximate contours and classify geometric shapes.
- Symmetry Detection: Implemented methods to detect symmetry through vertex reflection and perpendicular bisectors.
- Curve Regularization: After Shape Detection by extracting and adjusting their contours, fitting them to standard geometric models (like circles, ellipses, and polygons), and then visualizing these cleaned and consistent shapes to ensure they adhere to expected geometric properties.
- Visualization: Created side-by-side visual comparisons of original and processed curves.
- Batch Processing: Enabled automated processing of multiple datasets with results saved to CSV files.

## How to Run ⭐
- **Get Started Easily:** Running the solution is simple, we have compiled our solution in the [99_Accurate_Solution.ipynb](https://github.com/thejediboySHASHANK/CurveTopia_MythiCode_Pull/blob/main/99_Accurate_Solution.ipynb).
- Open that ```.ipynb``` Notebook either in Google Collab or local Jupyter Notebook by downloading it from the repository.
- Upload the ```problems``` dataset in the input file and adjust paths if necessary.
- Run through each cell to try and test out the solution

Please refer to the demo video to get a guided walkthrough on how to run the solution.

## Detailed Code Understanding 🔭

If you are interested in seeing detailed line-by-line code explanations, then please refer to this [Notion Page]().

## Future Vision 💯

While this repository is originally created for the ```Round - 2 of Adobe Genzolve```, we plan to extend the solution (irrespective of the result with further Adobe Rounds) as a project of free-hand draw canvas tool for note-taking or doodling SaaS, targetting specific product use-case niches.

## Contributing ✅

Liked the vision? Or
Liked my solution? Please feel free to star, raise a PR or fork to extend this project! 🚀
This is a really interesting and valuable project, collaborators are always welcomed!

## Solution for Adobe GenSolve CurveTopia by Team MythiCode Pull

## Table of Contents 📃
- [Approach](#approach)
- [How to Run](#how-to-run)
- [Overview](#overview)
- [Current Integrations & Planned](#current-integrations--planned)
- [Demo](#demo-pics)
- [Contributing](#contributing)

## Approach 📌

We tried and tested multiple solutions through trial and error, combining multiple technologies:
- R-CNN for Shapes Detection
- Pure OpenCV Countours based approach
- RDP Algorithm for shape simplification as smoothing
- Image Segmentation for Shape Detections

However, the best solution as highlighted in [99_Accurate_Solution.ipynb](https://github.com/thejediboySHASHANK/CurveTopia_MythiCode_Pull/blob/main/99_Accurate_Solution.ipynb),
was achieved through a meticulate combination of all the above listed trials, errors and optimizations on top of that.

- Dataset Import: Automated CSV file import and preprocessing for geometric data.
- Curve Grouping: Classified segments into open and closed curves based on connectivity.
- Shape Identification: Using OpenCV + Basic Geometric shapes formulas (Areas, Perimeter, radius, etc) to approximate contours and classify geometric shapes.
- Symmetry Detection: Implemented methods to detect symmetry through vertex reflection and perpendicular bisectors.
- Curve Regularization: After Shape Detection by extracting and adjusting their contours, fitting them to standard geometric models (like circles, ellipses, and polygons), and then visualizing these cleaned and consistent shapes to ensure they adhere to expected geometric properties.
- Visualization: Created side-by-side visual comparisons of original and processed curves.
- Batch Processing: Enabled automated processing of multiple datasets with results saved to CSV files.

## How to Run
- **Get Started Easily:** Running the solution is simple, we have compiled our solution in the [99_Accurate_Solution.ipynb](https://github.com/thejediboySHASHANK/CurveTopia_MythiCode_Pull/blob/main/99_Accurate_Solution.ipynb).
- Open that ```.ipynb``` Notebook either in Google Collab or local Jupyter Notebook by downloading it from the repository.
- Upload the ```problems``` dataset in the input file and adjust paths if necessary.
- Run through each cell to try and test out the solution

Please refer to the demo video to get a guided walkthrough on how to run the solution.

## Overview 🔭

**OrchestrAI**  is a cutting-edge no-code automation tool designed to streamline and simplify complex workflows through seamless AI integration. It empowers users to create sophisticated automation systems with ease, merging AI technologies like GPT and Gemini to enhance efficiency and productivity across various applications.

### Key Features ⚡

- **No-Code Tool**: Easily create complex automations without writing a single line of code.
- **AI Integration**: Seamlessly integrate with AI technologies to enhance functionality.
- **Customizable Workflows**: Tailor workflows to meet the specific needs of your processes.
- **User-Friendly Interface**: A clean, intuitive interface that makes automation accessible to everyone.

### How It Works ✅

OrchestrAI leverages Google Drive as an action trigger (for now, click here to see future integrations being developed) to initiate workflows that integrate seamlessly with other applications like Discord, Slack, and Notion. 
When a specified event occurs in Google Drive, such as a new file upload or update, 
OrchestrAI activates the designated actions in the connected services to facilitate real-time responses and automate tasks efficiently.

### Setting Up Your First Workflow ⭕

1. **Define the Trigger**:
   Configure Google Drive as the trigger. Specify the events within Google Drive that should start the workflow.

2. **Configure the Actions**:
   Choose and set up the actions that should be executed in Discord, Slack, or Notion once the trigger event occurs.

3. **Test and Deploy**:
   Test the workflow thoroughly to ensure that it functions as intended. Once confirmed, deploy it to automate your tasks without further manual intervention.

## Current Integrations & Planned 🧑‍💻

<div align="center">

| Integration  | Type        | Status           | Description                                                  |
|--------------|-------------|------------------|--------------------------------------------------------------|
| Google Drive | Trigger     | Active           | Listens for any changes and initiates workflows.             |
| Discord      | Listener    | Active           | Receives notifications and automates responses.              |
| Slack        | Listener    | Active           | Automates notifications and task-related workflows.          |
| Notion       | Listener    | Planned          | Future integration for document and knowledge management.    |
| ChatGPT      | Trigger/Listener    | Planned          | Planned for enhancing interactive and automated responses.   |
| Google Sheets| Trigger/Listener    | Planned          | Planned for automating data-driven tasks and analysis.       |
| Gmail        | Trigger/Listener    | Planned          | Planned for automating email-based workflows and alerts.     |
| WhatsApp     | Trigger/Listener    | Planned          | Planned for messaging and notifications automation.          |
| Telegram     | Trigger/Listener    | Planned          | Planned for secure messaging and automation of communications.|

</div>

## Demo Pics

![image](https://github.com/user-attachments/assets/0699c2bc-c807-446a-9ec3-d33b68f343af)
![image](https://github.com/user-attachments/assets/ec4bf2f3-0d98-4ffd-bc2b-bd70c05e2f65)


## Contributing

Liked my project? Please feel free to star, raise a PR or fork to extend this project! 🚀
This is a big and impactful project, collaborators are always welcomed!

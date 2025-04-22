# Smart_Irrigation_Enhancing_Water_Management-Project

This repository contains a machine learning model for predicting water requirements for irrigation based on environmental parameters.

## Running in Google Colab

### Quick Start

1. Open the notebook in Google Colab by clicking this button: https://colab.research.google.com/drive/1oy-jWAf2er_nX8ZrwDK1ebzERUTWgoXd?usp=sharing

2. Connect to a runtime by clicking the "Connect" button in the top-right corner of Colab.

3. Run all cells: Click on "Runtime" in the menu, then "Run all" (or press Ctrl+F9).

### Step-by-Step Instructions

1. **Mount Google Drive** (optional but recommended for saving models):
   - Run the cell containing:
     ```python
     from google.colab import drive
     drive.mount('/content/drive')
     ```
   - Follow the authorization prompts to connect your Google Drive.

2. **Install Required Dependencies**:
   - The notebook includes a cell with all necessary installations:
     ```python
     !pip install tensorflow pandas matplotlib scikit-learn seaborn gradio xarray scipy pillow
     ```

3. **Upload the Dataset**:
   - If using example NC4 files, upload them to Colab under sample data.
   - Alternatively, the model can generate synthetic data if no real data is available.

4. **Choose Execution Mode**:
   - For training: Set `mode = "train"` in the configuration cell
   - For evaluation: Set `mode = "evaluate"` in the configuration cell
   - For demo interface: Set `mode = "demo"` in the configuration cell

5. **Run the Interface**:
   - When running in demo mode, Colab will display a public URL for accessing the Gradio interface
   - Click on the URL to open the water requirement prediction tool in a new tab
   - Use the sliders to adjust environmental parameters and predict irrigation requirements

6. **Save Trained Models** (if training):
   - Models will be saved to the Colab environment by default
   - To save to Google Drive for persistence, modify the config paths:
     ```python
     config['output_model_path'] = '/content/drive/MyDrive/models/water_requirement_model.h5'
     config['output_pickle_path'] = '/content/drive/MyDrive/models/water_requirement_model.pkl'
     ```

7. **View Evaluation Results**:
   - Performance metrics and visualizations will be displayed after training or evaluation
   - Confusion matrices and prediction accuracy charts are automatically generated

### Troubleshooting

- **Memory Issues**: If you encounter memory errors, try:
  - Using a Colab runtime with more RAM (Runtime → Change runtime type → Hardware accelerator: GPU)
  - Reducing the `batch_size` in the config dictionary
  - Setting `config['spatial_dims'] = (8, 8)` for smaller spatial dimensions

- **Runtime Disconnects**: For long training sessions, keep the Colab tab active or use a GPU runtime to complete training faster

- **Missing Dependencies**: If you encounter import errors, run the pip install cell again to ensure all packages are installed

### Loading Pre-trained Models

To use an existing pre-trained model:
1. Upload your model files to Colab or Google Drive
2. Update the model paths in the config:
   ```python
   config['output_model_path'] = 'path/to/your/model.h5'
   config['output_pickle_path'] = 'path/to/your/model.pkl'


![image](https://github.com/user-attachments/assets/18e444d9-5b17-4213-a84a-a7223a80cbc9)

![image](https://github.com/user-attachments/assets/2945a483-2c70-47ab-b20d-1a2adaf0018c)

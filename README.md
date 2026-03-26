<div align="center">
  <h1>Automated Malaria Parasite Detection and Red Blood Cell Quantification</h1>
  <p><i>An Rule-Based Digital Image Processing Framework</i></p>
</div>

## Abstract

This work presents a computational framework for the automated detection of malaria parasites and quantification of red blood cells (RBCs) in Giemsa-stained microscopic blood smear images. Developed as a Complex Engineering Problem (CEP), the system is implemented in Python and strictly adheres to classical image processing methodologies, avoiding machine learning or deep learning techniques.

The proposed rule-based approach ensures transparency, interpretability, and computational efficiency. The framework effectively addresses challenges such as illumination inconsistencies, staining variability, and cellular overlap. Additionally, interactive parameter tuning enables adaptability across diverse imaging conditions. The system produces visually verifiable outputs alongside quantitative parasitemia metrics.

> **Disclaimer:** This system is intended solely for academic and research purposes and is not certified for clinical diagnostic use.


## 1. Introduction

Malaria diagnosis through microscopic examination remains a critical yet labor-intensive process. Automating parasite detection can significantly enhance diagnostic efficiency and consistency. While modern solutions often rely on deep learning, such approaches lack interpretability.

This project proposes a deterministic, rule-based pipeline grounded in classical computer vision techniques. Each computational step is mathematically defined and visually verifiable, making the system suitable for educational and analytical applications.


## 2. Methodology

### 2.1 Preprocessing

The input image undergoes:
- Resizing for computational efficiency  
- Grayscale conversion  
- Contrast enhancement using CLAHE  
- Gaussian filtering to reduce noise  

### 2.2 Field-of-View (FOV) Demarcation

A binary mask isolates the active microscopic region, eliminating dark peripheral areas to reduce false detections.

### 2.3 Erythrocyte Localization

Circular Hough Transform (CHT) is employed to detect RBCs. Post-processing techniques eliminate overlapping and duplicate detections to ensure spatial accuracy.

### 2.4 Chrominance Segmentation

The image is converted to HSV color space. Thresholding is applied to isolate magenta-stained malaria parasites, improving robustness against illumination variations.

### 2.5 Leukocyte Exclusion

Connected component analysis identifies large regions corresponding to white blood cell nuclei. These are removed based on area thresholds to prevent misclassification.

### 2.6 Infection Classification

Each detected RBC is evaluated for parasite presence. If parasite pixels exceed a defined threshold, the cell is classified as infected.

The parasitemia is computed as:

Parasitemia (%) = Number of infected RBCs / Total number of RBCs * 100


## 3. Results and Visual Interpretation

The system generates annotated overlays for validation:

| Indicator | Description |
|----------|------------|
| 🟢 Green Circles | Detected RBC boundaries |
| 🔴 Red Markers | Detected malaria parasites |

These visual outputs enable direct verification of algorithmic decisions.


## 4. System Workflow

1. Image Acquisition  
2. Parameter Calibration  
3. Visual Analysis  

The system includes adjustable parameters such as:
- Circular Hough Transform sensitivity  
- HSV threshold ranges  


## 5. Key Features

- Rule-based and interpretable pipeline  
- Robust against illumination and staining variations  
- Accurate RBC detection using geometric methods  
- HSV-based parasite detection  
- Automatic parasitemia computation  
- Real-time visual verification  

## 6. Live Demo

Upload a smear image. Tune parameters in sidebar. Green circles = RBCs, red dots = infected RBC centers. 
Educational use only.

Live Demo: https://dip-cep-malaria-detection.streamlit.app/
Test images are provided in the test_image folder.

## 7. Conclusion

This work demonstrates that classical image processing techniques can effectively address complex biomedical image analysis tasks. The proposed framework provides a transparent and computationally efficient alternative to black-box AI systems.

While not suitable for clinical deployment, the system serves as a strong foundation for academic research and future hybrid approaches integrating explainable AI.


## 8. Authors and Affiliation

- Souman Ahmad (22-EE-07)  
- Hamza (22-EE-51)  
- Saqib Shehzad (22-EE-53)  
- Tahzeeb-Ul-Hassan (22-EE-95)  

**Department of Electrical Engineering**  
**University of Engineering and Technology (UET), Taxila**

## 9. Academic Supervision

**Dr. Junaid Mir, Assistant Professor, UET Taxila**


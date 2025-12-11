# VLM-CADFeatureRecognition
[![Dataset](https://img.shields.io/badge/Dataset-MFCAD--VLM-green)](https://zenodo.org/records/14038050)


This repository contains the code and resources accompanying the paper "[Leveraging Vision-Language Models for Manufacturing Feature Recognition in CAD Designs](https://arxiv.org/abs/2411.02810)". The study explores the application of vision-language models (VLMs) to automate the recognition of various manufacturing features in CAD designs without extensive training datasets or predefined rules.

**Dataset Used:** The dataset used in this study is available in the `Dataset` folder.

**Authors:** [Chen Lequn](https://github.com/Davidlequnchen), [Muhammad Tayyab Khan](https://github.com/tayyabkhan3)


## Overview

Automatic Feature Recognition (AFR) is crucial for converting design knowledge into actionable manufacturing information. Traditional AFR methods often rely on predefined geometric rules and large datasets, which can be time-consuming and may lack generalizability across different manufacturing features. This project investigates the use of VLMs, employing prompt engineering techniques such as multi-view query images, few-shot learning, sequential reasoning, and chain-of-thought, to recognize a wide range of manufacturing features in CAD designs.


<p align="center">
  <img src="doc/Methdology_overview.png" alt="Methodology Overview" width="80%">
  <br>
  <em>Figure 1: Overview of VLM-based AFR approach</em>
</p>

<!-- <p align="center">
  <img src="doc/Prompt_engineering-few-shot-2.png" alt="Few-Shot Prompt Engineering" width="80%">
  <br>
  <em>Figure 2: Few-shot learning for VLM-driven AFR</em>
</p>

<p align="center">
  <img src="doc/Dataset-Dataset_glance.png" alt="MFCAD-VLM Dataset Overview" width="80%">
  <br>
  <em>Figure 3: MFCAD-VLM dataset for CAD feature recognition</em>
</p>

<p align="center">
  <img src="doc/Dataset-easy-1.png" alt="Example of Easy Dataset" width="80%">
  <br>
  <em>Figure 4: Example of an easy CAD feature recognition task</em>
</p>

<p align="center">
  <img src="doc/Dataset-Hard-1.png" alt="Example of Hard Dataset" width="80%">
  <br>
  <em>Figure 5: Example of a complex CAD feature recognition task</em>
</p> -->

## MFCAD-VLM Dataset

The study utilizes the [MFCAD-VLM dataset](https://zenodo.org/record/14038050), a comprehensive collection designed to advance research in CAD and AFR. The dataset includes:

- **STEP Files**: CAD models in STEP format, representing various parts with distinct manufacturing features, categorized by complexity levels (easy, medium, and hard).
- **Ground Truth JSON Files**: Expert-annotated JSON files corresponding to each STEP file, detailing manufacturing feature types, quantities, and specifics essential for accurate AFR assessment.
- **Multi-View Isometric Images**: Three isometric-view snapshots per CAD model, generated via Python, capturing different viewing angles to aid feature recognition tasks.


## Installation

### Requirements
- Python >= 3.9
- PyTorch >= 1.8.0
- CUDA-compatible GPU (recommended) with appropriate CUDA drivers installed

To set up the environment, follow these steps:

1. **Clone the repository**:

   ```bash
   git clone https://github.com/Davidlequnchen/VLM-CADFeatureRecognition.git
   cd VLM-CADFeatureRecognition
   ```

2. **Create and activate a conda environment**:

   ```bash
   conda create -n vlm_afr python=3.9
   conda activate vlm_afr
   ```

3. **Install pyocc using conda**:

   ```bash
   conda install -c conda-forge pythonocc-core=7.8.1
   ```

4. **Install PyTorch**:

   To check your CUDA version:
   ```bash
   nvidia-smi
   ```

   IMPORTANT: PyTorch installation depends on your CUDA version. Choose the appropriate command:

   For CUDA 12.1:
   ```bash
   pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121
   ```

   For CUDA 11.8:
   ```bash
   pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118
   ```

   For CPU only:
   ```bash
   pip install torch torchvision torchaudio
   ```

5. **Install other requirements**:

   ```bash
   pip install -r requirements.txt
   ```

## Usage

1. **Download the MFCAD-VLM Dataset**:

   Access and download the dataset from [Zenodo](https://zenodo.org/record/14038050). Extract the contents to `"Dataset"` directory.

2. **Configure the Dataset Path**:

   Set the path to the directory where the MFCAD-VLM dataset is located.

3. **Run Experiments**:

   Execute the provided scripts to perform feature recognition tasks as described in the paper. 


## 📄 Citation

If you find this repository or the MFCAD-VLM dataset useful in your research, please cite our officially published paper:

**Leveraging Vision-Language Models for Manufacturing Feature Recognition in Computer-Aided Designs**  
*Journal of Computing and Information Science in Engineering (JCISE), ASME, 2025.*  
**DOI:** [https://doi.org/10.1115/1.4069266](https://doi.org/10.1115/1.4069266)

```bibtex
@article{khan2025leveraging,
  title={Leveraging Vision-Language Models for Manufacturing Feature Recognition in Computer-Aided Designs},
  author={Khan, Muhammad Tayyab and Chen, Lequn and Ng, Ye Han and Feng, Wenhe and Tan, Nicholas Yew Jin and Moon, Seung Ki},
  journal={Journal of Computing and Information Science in Engineering},
  volume={25},
  number={},
  pages={104501},
  year={2025},
  publisher={American Society of Mechanical Engineers},
  doi={10.1115/1.4069266},
  url={https://doi.org/10.1115/1.4069266}
}


## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgements

We acknowledge the support from the Singapore Institute of Manufacturing Technology (SIMTech), the Advanced Remanufacturing and Technology Centre (ARTC), and Nanyang Technological University (NTU).

# 📜 Instructions

## ⚙️ Configurations
The source code requires the following dependencies:

* **PyTorch** = 1.7.0
* **Torchvision** = 0.8.1
* **CUDA** = 10.1
* **PyYAML** = 5.1

Ensure these dependencies are installed before proceeding.

## 📷 Detectron2
The table detection model is based on [Detectron2](https://github.com/facebookresearch/detectron2). Follow the official [installation guide](https://detectron2.readthedocs.io/en/latest/tutorials/install.html) to set it up correctly.

## 🖼️ Image Alignment Pre-Processing
For image alignment pre-processing, use the following script:

* **`deskew.py`**

To apply the image alignment algorithm to all images in a folder, run:

```bash
python3 deskew.py --folder <input_folder> --output <output_folder>
```

### 📝 Parameters:
* `--folder` : Path to the input folder containing document images.
* `--output` : Path to the output folder where the deskewed images will be saved.

## 📑 Table Structure Recognition
For table structure recognition, use:

* **`tsr.py`**

To apply the table structure recognition algorithm to all images in a folder, run:

```bash
python3 tsr.py --folder <input_folder> --type <table_type> --img_output <image_output_folder> --xml_output <xml_output_folder>
```

### 📝 Parameters:
* `--folder` : Path to the input folder containing table images.
* `--type` : Type of table structure recognition (options: `bordered`, `unbordered`, `partially`, `partially_color_inv`).
* `--img_output` : Path to the output folder for processed images.
* `--xml_output` : Path to the output folder for XML files containing bounding boxes.

## 📊 Table Detection and Table Structure Recognition
To perform table detection followed by table structure recognition, use:

* **`tdtsr.py`**

Run the script with the following command:

```bash
python3 tdtsr.py --folder <input_folder> --type <table_type> --tsr_img_output <tsr_output_folder> --td_img_output <td_output_folder> --xml_output <xml_output_folder> --config <config_path> --yaml <yaml_path> --weights <weights_path>
```

### 📝 Parameters:
* `--folder` : Path to the input folder containing table images.
* `--type` : Table structure recognition type (`bordered`, `unbordered`, `partially`, `partially_color_inv`).
* `--tsr_img_output` : Output folder for processed table images.
* `--td_img_output` : Output folder for table cutouts.
* `--xml_output` : Output folder for XML files containing table and cell bounding boxes.
* `--config` : Path to the Detectron2 configuration file for table detection.
* `--yaml` : Path to the Detectron2 YAML file for table detection.
* `--weights` : Path to the Detectron2 model weights for table detection.

## 📈 Evaluation
To evaluate the table structure recognition algorithm, use:

* **`evaluate.py`**

Ensure that table images and their corresponding XML labels have the same name and are located in a single folder.

Run the evaluation script using:

```bash
python3 evaluate.py --dataset <dataset_folder>
```

### 📝 Parameters:
* `--dataset` : Path to the dataset folder containing table images and corresponding XML labels.

---

# IPCV Project

University project for the _Image Processing and Computer Vision_ course (University of Bologna).
The repository contains two self-contained assignments delivered as Jupyter notebooks:

- **Module 1 — Product Recognition of Books (traditional CV)**
- **Module 2 — Pet Classification (deep learning with PyTorch)**

Licensed under the MIT License.

---

## Contents

```
.
├── assignment_module_one.ipynb     # Module 1: Book detection on shelf images (classical CV)
├── assignment_module_two.ipynb     # Module 2: Oxford-IIIT Pet classification (DL)
├── dataset/                        # Data for Module 1
│   ├── models/                     # One reference image per book (model_0.png, …)
│   └── scenes/                     # Shelf photos to analyze (scene_0.jpg, …)
├── LICENSE                         # MIT
├── .gitignore
└── .gitattributes
```

The dataset for Module 1 is versioned in this repo under `dataset/models` and `dataset/scenes`.

---

## Module 1 — Product Recognition of Books

**Goal.** Given a set of reference images (one per book) and a set of scene images (shelves), detect all instances of each book in the scenes and report, for every instance:

- the aligned bounding box (four corners),
- the instance area (in pixels),
- the instance count per book,
- and an overlay visualization on the scene.

**Approach (high level).** The notebook implements a traditional computer-vision pipeline (no deep learning), using standard techniques such as feature matching / template matching, geometric verification, and image processing to localize and count book spines/covers. (As required by the assignment brief to rely on classical CV methods.)

**Data.**

- `dataset/models/`: reference images (e.g., `model_0.png … model_21.png`)
- `dataset/scenes/`: shelf photos (e.g., `scene_0.jpg … scene_28.jpg`)

**Outputs.** The notebook prints per-book summaries and renders overlays of detected bounding boxes on the corresponding scene images.

---

## Module 2 — Pet Classification

**Goal.** Train an image classifier for **37** cat/dog breeds using the **Oxford-IIIT Pet** dataset. The assignment is split into two parts:

1. implement a simple CNN from scratch; 2) fine-tune a pretrained model with PyTorch.

**Dataset.** The notebook fetches a prepared split for the course by cloning `CVLAB-Unibo/ipcv-assignment-2`. The underlying data correspond to the Oxford-IIIT Pet dataset (37 classes, \~200 images per class).

**Workflow (high level).**

- Data loading utilities (`OxfordPetDataset`) for the provided train/val/test split.
- Training loops for a custom CNN and for fine-tuning a pretrained backbone.
- Evaluation with standard classification metrics.

_Oxford-IIIT Pet official page:_ Visual Geometry Group, University of Oxford.

---

## Getting Started

### Environment

- Python 3.x with Jupyter
- Common scientific stack (NumPy, Matplotlib, etc.)
- **Module 1:** OpenCV
- **Module 2:** PyTorch & torchvision

### Run the notebooks

1. **Clone this repository** and open it in Jupyter/Colab.
2. **Module 1:** `assignment_module_one.ipynb`
   Uses the local `dataset/` folder included in the repo (no additional downloads).
3. **Module 2:** `assignment_module_two.ipynb`
   The first cells clone the course dataset repo (`ipcv-assignment-2`) and set up the dataset class; run the cells as provided.

---

## Repository Status & Authorship

- **Authors:** Alberto Benni (Albenni), Filippo Terzi (thefffilo).
- **License:** MIT (see `LICENSE`).

# Knowledge-Driven Vision-Language Model for Plexus Detection in Hirschsprung’s Disease
*Youssef Megahed*<sup>†</sup>, *Atallah Madi*<sup>†</sup>, *Dina El Demellawy, Adrian D. C. Chan*

<sup>†</sup> These authors contributed equally as first co-authors.

[![arXiv](https://img.shields.io/badge/arXiv-2510.21083-b31b1b.svg)](https://arxiv.org/abs/2510.21083)

## 📋 Overview

This project proposes a novel framework that integrates expert-derived textual concepts into a CLIP-based vision-language model to guide plexus classification in histopathological whole slide images (WSIs) for Hirschsprung’s Disease (HD).  
This method combines domain-specific medical knowledge with deep learning to improve interpretability and alignment with real-world diagnostic processes.

**Accepted into the ICAAI 2025 - The 9th International Conference on Advances in Artificial Intelligence at Manchester, UK!**

## ✨ Highlights

- **Baseline Models:** VGG-19 (baseline), ResNet-18, and ResNet-50 CNNs fine-tuned on histopathological tiles. 
- **Proposed Model:** CLIP-based multi-modal model integrating expert prompts.
- **Dataset:** 30 WSIs from 26 patients (Children’s Hospital of Eastern Ontario). The dataset folder will be left empty, as this is a private dataset and cannot be shared publicly. 
- **Results:**  
  - VGG-19 achieved 79.40% accuracy, 78.38% precision, and 77.60% specificity.
  - ResNet-18 achieved 58.91% accuracy, 57.60% precision, and 50.29% specificity.  
  - ResNet-50 achieved 56.95% accuracy, 54.36% precision, and 27.23 % specificity.  
  - Proposed CLIP-based model (QuiltNet) achieved 83.93% accuracy, 86.61% precision, and 87.60% specificity, showing stronger discriminative ability overall.  
- **Contribution:** Demonstrates how expert knowledge can enhance model reasoning in medical imaging tasks.

## 📂 Project Structure
```
KDVLM/
├── ConcepPath/
├── dataset/
├── experiment/plexus_detection/
├── prompts/
├── reports/
├── saved_rp_all/          # Pre-trained features and model checkpoints
├── best_model.pt          # Best trained model weights
├── Fold_1_5_Epoch_Metrics.csv  # Training metrics for cross-validation
├── README.md # Project description and instructions
├── Tutorial.ipynb
├── creating_labels.ipynb
├── report_visuals.ipynb
├── training_setup.ipynb
├── training_setup_v2.ipynb
```

## 🧪 Methodology

- **Data Preprocessing:**
  - Macenko colour normalization
  - Downsampling WSIs from 20x to 5x magnification
  - Extraction of 224×224 overlapping tiles (50% overlap)
- **Baseline CNN Models:**
  - VGG-19, ResNet-18, and ResNet-50 fine-tuned with 5-fold cross-validation 
- **Proposed CLIP-based Model:**
  - Textual prompts extracted using LLMs (e.g., GPT-4o, DeepSeek-R1)
  - Concept-guided hierarchical aggregation
  - Vision and text encoders from QuiltNet (trained on Quilt-1M dataset), fine-tuned with 5-fold cross-validation 

## 🔥 Results

| Model                | Accuracy (%) | Precision (%) | Recall (%) | Specificity (%) | F1 Micro (%) | F1 Macro (%) | AUC (%) |
|:---------------------|:------------:|:-------------:|:----------:|:---------------:|:------------:|:------------:|:-------:|
| VGG-19 (Baseline)    | 79.40        | 78.38         | 81.20      | 77.60           | 79.40        | 79.02        | 89.13   |
| ResNet-18            | 58.91        | 57.60         | 67.52      | 50.29           | 58.91        | 55.74        | 64.12   |
| ResNet-50            | 56.95        | 54.36         | **86.67**  | 27.23           | 56.94        | 51.53        | 64.67   |
| QuiltNet (Proposed)  | **83.93**    | **86.61**     | 80.24      | **87.60**       | **83.93**    | **83.86**    | **91.76** |

The QuiltNet model showed higher AUC, indicating better overall discriminative power.

## 🏥 Clinical Impact

By aligning AI predictions with expert-driven medical concepts, this method offers enhanced interpretability, better diagnostic consistency, and the potential to aid pathologists in clinical settings.

## 🚀 Future Work

- Expand prompt diversity to improve classification robustness.
- Acquire larger annotated datasets.

## 🙏 Acknowledgments

This project incorporates code from the **ConcepPath** repository, which was developed by its original authors. We acknowledge and thank them for their contributions to concept-based vision-language modeling (Original ConcepPath code: [GitHub Repository](https://github.com/HKU-MedAI/ConcepPath).

If you use or build upon the *ConcepPath* components included in this repository, please ensure you also cite their work accordingly.

## 📚 Please Cite

```bibtex
@article{megahedmadi2025kdvlm,
  title={Knowledge-Driven Vision-Language Model for Plexus Detection in Hirschsprung’s Disease},
  author={Youssef Megahed and Atallah Madi and Dina El Demellawy and Adrian D. C. Chan},
  year={2025},
  eprint={2510.21083},
  archivePrefix={arXiv},
  primaryClass={cs.CV},
  url={https://arxiv.org/abs/2510.21083},
}
```

📧 Contact: youssefmegahed@cmail.carleton.ca or atallahmadi@cmail.carleton.ca

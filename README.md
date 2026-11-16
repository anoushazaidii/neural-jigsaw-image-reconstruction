# Neural Jigsaw Image Reconstruction Using Deep Learning

A computer vision project that reconstructs original images from nine randomly shuffled patches using a hybrid CNN-Transformer architecture.

## Overview

This project explores image reconstruction using deep learning. Images from the STL-10 unlabelled dataset are divided into a 3×3 grid, shuffled, and provided to a neural network. The model learns to recover the original image directly from the shuffled patches.

Unlike a conventional jigsaw puzzle solver that predicts a fixed patch permutation, this approach uses learned soft patch assignments and an image reconstruction objective.

## Architecture

The model consists of three main components:

1. **CNN Feature Extractor:** Extracts visual features independently from each image patch.
2. **Transformer Encoder:** Uses four Transformer blocks with multi-head self-attention to learn relationships between patches.
3. **Image Reconstruction Network:** Uses soft patch assignment to construct an initial image canvas, followed by convolutional refinement layers to produce the final reconstruction.

## Workflow

1. Load and preprocess STL-10 unlabelled images.
2. Divide each 96×96 RGB image into a 3×3 grid.
3. Crop and shuffle the nine patches.
4. Extract patch-level visual features.
5. Learn patch relationships through Transformer attention.
6. Generate a reconstructed image.
7. Evaluate reconstruction quality using Mean Absolute Error (MAE).

## Technical Details

| Parameter | Value |
|---|---|
| Dataset | STL-10 Unlabelled |
| Image resolution | 96×96 |
| Patch grid | 3×3 |
| Number of patches | 9 |
| Patch dimensions | 28×28×3 |
| Transformer blocks | 4 |
| Attention heads | 4 |
| Batch size | 64 |
| Maximum epochs | 96 |
| Learning rate | 0.001 |
| Loss function | MAE |
| Total parameters | 974,771 |

## Results

The completed Kaggle training run reported the following test-set results:

- Test images evaluated: 10,000
- Mean Test MAE: 0.034867
- Test MAE Standard Deviation: 0.043477

Lower MAE indicates better pixel-level reconstruction.

## Technologies Used

- Python
- TensorFlow
- Keras
- NumPy
- Matplotlib
- Computer Vision
- Convolutional Neural Networks
- Transformer Architecture
- Self-Attention
- 
## Reproducibility

The original full training configuration was executed using Kaggle. The notebook also includes a lightweight Google Colab verification mode.

To reproduce the full training, provide the STL-10 dataset, configure the Kaggle environment, and enable the training mode.

## Academic Context

Developed as part of the Deep Learning coursework for the MSc in Artificial Intelligence at the University of Bologna.

## Future Improvements

- Explore alternative attention mechanisms.
- Improve reconstruction quality through additional training experiments.
- Investigate different patch sizes and grid configurations.
- Compare CNN-Transformer reconstruction with alternative architectures.

## License

Add an appropriate license after checking the permissions and licensing of any third-party code and assets.

# Ayna-ML

# Polygon Colorization using Conditional UNet

This project implements a UNet model trained from scratch to generate colored polygon images, conditioned on:

- A polygon outline image (e.g., triangle, star, octagon)
- A color name (e.g., blue, yellow, green)

The model outputs the polygon filled with the requested color.

---

## Dataset

- Paired images: input polygon outlines and target colored polygons
- 8 possible color classes
- Separate training and validation splits, each with RGB images and mapping metadata

## Model

- **Architecture:** Conditional UNet in PyTorch  
- **Color Conditioning:** One-hot color vector, spatially broadcast and concatenated to input image channels
- **Structure:** 2 down / 2 up blocks, batch normalization, skip connections, ReLU, sigmoid output
- **Output:** RGB image of the colored polygon

## Training Configuration

- **Optimizer:** Adam (learning rate 0.001)
- **Loss:** Mean Squared Error (MSE)
- **Batch size:** 32
- **Epochs:** 200
- **Image size:** 128 × 128 px
- **Experiment tracking:** [wandb](https://wandb.ai/aayushsingh8217-indian-institute-of-information-technology/polygon-unet)

## Results

- **Loss:** Stable convergence in both train and validation curves, with no overfitting
- **Qualitative Output:** The model reliably fills polygons with the instructed color; sharp shapes and vivid coloring achieved by epoch 200

## Practical Usage

- A Jupyter Notebook demonstrates loading the model, running inference with sample polygons and colors, and visualizing predictions.
- Minimal code required to adapt for new polygons or unseen color requests.

## Recommendations for Improvement

- Use data augmentation (rotation, scaling, noise) for greater robustness
- Explore more advanced conditioning (FiLM, learned embeddings) for color
- Try perceptual or boundary-aware loss for sharper results
- Experiment with learning rate scheduling for fine-tuned convergence

---

## Project Link

For logs, models, and sample outputs:
[https://wandb.ai/aayushsingh8217-indian-institute-of-information-technology/polygon-unet](https://wandb.ai/aayushsingh8217-indian-institute-of-information-technology/polygon-unet)

---

**Author:** Aayush Singh

# 🎮 Scarlet Moon: Pixel Art Generator

![Pixel Art Generation Process](https://img.freepik.com/premium-photo/pixel-art-animation-tranquil-desert-temple-horizon_899449-53687.jpg)

A deep learning project that generates pixel art using a custom diffusion model architecture. Built with PyTorch, the model learns to create pixel-perfect sprites through a carefully crafted denoising process.

## 📚 Project Overview

Scarlet Moon is a conditional diffusion model that generates 16x16 pixel art sprites. It uses a custom ResNet architecture with temporal and contextual embeddings to create high-quality pixel art from random noise.

### Key Features

- **Custom ContextResNet Architecture**: Combines ResNet blocks with temporal and context embeddings
- **Progressive Denoising**: 500-step diffusion process for high-quality generation
- **MLflow Integration**: Complete experiment tracking and model versioning
- **Weights & Biases Support**: Real-time training visualization and metrics tracking
- **Conditional Generation**: Support for labeled sprite generation

## 🛠 Technical Architecture

### Model Components

1. **ResNet Blocks**
   - Custom residual connections
   - Batch normalization layers
   - Adaptive convolution channels

2. **Context Integration**
   - Temporal embeddings for diffusion steps
   - Conditional context embedding layer
   - Adaptive feature fusion

3. **Progressive Generation**
   - Multi-scale upsampling layers
   - Noise scheduling system
   - Controlled denoising process

## 🚀 Getting Started

### Prerequisites

```bash
pip install -r requirements.txt
```

Required packages:
- PyTorch
- MLflow
- Weights & Biases
- NumPy
- Pillow
- tqdm

### Dataset Preparation

```python
# Download the pixel art dataset
kaggle datasets download -d mohamedifqir/pixel-art
unzip pixel-art.zip -d pixel_art
```

### Training

```python
python scarlet_moon_pixel_art.py
```

Configuration options:
```python
config = {
    'timesteps': 500,
    'beta1': 1e-4,
    'beta2': 0.02,
    'height': 16,
    'batch_size': 100,
    'n_epoch': 100,
    'learning_rate': 1e-3
}
```

## 📊 Training Metrics

The model tracks several key metrics during training:
- MSE Loss per batch
- Epoch loss averages
- Generation quality metrics
- Training time and resource usage

Access these metrics through:
- MLflow UI: `mlflow ui`
- W&B Dashboard: Project "diffusion-model"

## 🎨 Generated Samples

The model saves generated samples at regular intervals in the `samples` directory. Sample generation can be triggered manually:

```python
samples = sample_images(model, config, device, num_samples=16)
save_image(samples, 'samples/generated_sprites.png')
```

## 📈 Model Performance

Current achievements:
- Quality Generation: Crisp, clear pixel art sprites
- Training Stability: Consistent loss reduction
- Generation Speed: ~2 seconds per sprite
- Memory Efficiency: Runs on consumer GPUs

## 🤝 Contributing

Feel free to contribute to this project. Areas for improvement:
- Model architecture optimizations
- Training speed improvements
- New sprite categories
- UI/UX for sprite generation

## 📝 License

This project is licensed under the MIT License - see the LICENSE file for details.

## 🙏 Acknowledgments

- Pixel art dataset contributors
- PyTorch community
- MLflow and W&B teams for their excellent tools
- Kaggle for hosting the dataset

## 📧 Contact

Mohamed Ifqir - mohamedifqir99@gmail.com
Blog Link: [My Website](https://medifqir.vercel.app/)


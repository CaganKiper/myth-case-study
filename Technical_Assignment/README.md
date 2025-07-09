# Sketch Generation via Diffusion Models

![Myth AI Logo](https://myth-ai.com/wp-content/uploads/2023/05/646f153be1e56.png)

## Project Overview

This project implements conditional generative diffusion models that learn to generate hand-drawn sketches in a stroke-by-stroke sequential manner. Rather than generating the entire sketch at once, the models mimic the sequential nature of human drawing, producing strokes one after another in a realistic and interpretable way.

The implementation uses the [Quick, Draw!](https://quickdraw.withgoogle.com/data/) dataset released by Google, which provides timestamped vector representations of user-drawn sketches across various object categories.

## Model Categories

Separate conditional diffusion models were trained for each of the following three categories:
- Cat
- Bus
- Rabbit

## Project Structure

```
Technical_Assignment/
├── Technical_Assignment.ipynb  # Main notebook with implementation
├── animations/                 # GIF animations of the generation process
│   ├── bus_generation.gif
│   ├── cat_generation.gif
│   └── rabbit_generation.gif
├── data/                       # Dataset files
│   ├── bus.ndjson
│   ├── cat.ndjson
│   └── rabbit.ndjson
├── models/                     # Trained model files
│   ├── bus_model.pth
│   ├── cat_model.pth
│   └── rabbit_model.pth
└── subset/                     # Train/test split indices
    ├── bus/
    │   └── indices.json
    ├── cat/
    │   └── indices.json
    └── rabbit/
        └── indices.json
```

## Setup Instructions

1. Clone this repository
2. Install the required dependencies:
   ```bash
   pip install torch torchvision matplotlib pandas numpy ndjson gsutil
   ```
3. The dataset files are already included in the `data/` directory

## Usage

1. Open the `Technical_Assignment.ipynb` notebook in Jupyter or your preferred notebook environment
2. Run the cells sequentially to:
   - Load and preprocess the data
   - Train the diffusion models
   - Generate sketch samples
   - Evaluate model performance

## Model Details

The implementation uses diffusion models to generate sequential stroke data. Each model:
- Learns the distribution of strokes for a specific category
- Generates sketches in a stroke-by-stroke manner
- Mimics the natural drawing process of humans

## Results

The models were evaluated using both qualitative and quantitative metrics:
- Qualitative: Visual inspection of generated samples
- Quantitative: FID (Fréchet Inception Distance) and KID (Kernel Inception Distance) scores

Sample animations of the generation process can be found in the `animations/` directory.

## References

- [What are Diffusion Models?](https://lilianweng.github.io/posts/2021-07-11-diffusion-models/)
- [Teaching Machines to Draw](https://research.google/blog/teaching-machines-to-draw/)
- [Quick, Draw! Dataset](https://quickdraw.withgoogle.com/data/)
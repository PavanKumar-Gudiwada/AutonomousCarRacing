This project was completed as part of my graduate coursework and focuses on building and evaluating deep learning models for autonomous driving in the Gym CarRacing-v0 environment. The work explores both Convolutional Neural Networks (CNNs) for perception from raw images and Recurrent Neural Networks (RNNs/GRUs) for capturing temporal dependencies in driving behavior.

# Project Workflow
1. Data Collection
- Collected driving data by manually controlling the car in the CarRacing-v0 environment.
- Frames and corresponding control actions (steering, acceleration, braking) were logged to create a supervised learning dataset.

2. Model Training
- CNN Model: Trained to predict driving actions directly from pixel inputs.
- RNN/GRU Model: Extended to handle sequential frame information, leveraging temporal context for smoother driving performance.

3. Model Optimization & Evaluation
- Applied post-training quantization to reduce model size and improve inference efficiency.
- Experimented with Quantization-Aware Training (QAT) to mitigate accuracy loss and compared results against the original CNN baseline.

# Key Highlights
- Demonstrates a full ML workflow: data generation → supervised training → optimization → evaluation.
- Evaluates trade-offs between standard CNNs and temporal models (RNN/GRU) in autonomous decision-making.
- Provides comparison between baseline models, quantized models, and QAT models to analyze performance vs efficiency.

# Tech Stack
- Python, PyTorch for deep learning
- OpenAI Gym (CarRacing-v0) for environment simulation
- Numpy and Matplotlib for dataset handling and analysis

# Results & Observations

## Model Performance
|Model|Regression MSE|Model Size|Inference Time|FLOPs|
|:---|:---:|---:|---:|---:|
|CNN|0.0312|9.99 MB|0.0170s|66.87 Mega FLOPs|
|CNN (quantised)|0.0607|2.52 MB|0.0140s|0|
|CNN (QAT)|0.0134|2.52MB|0.0102s|0|
|RNN (GRU)|0.2729|28.18 MB|0.0089s|716.41 Mega FLOPs|

## Model Comparison
- Temporal Awareness:
The RNN/GRU model demonstrated improved stability and smoother control by utilizing frame histories, especially in high-curvature track sections.

- Quantization Impact:
Post-training quantization significantly reduced the CNN model size and inference latency with a drop in MSE loss.
Quantization-Aware Training (QAT) retained better MSE loss, with improved inference time compared to the original floating point model.

- Trade-offs:
Classic CNNs are faster but less robust on temporally complex driving scenarios.
RNN/GRUs, while slightly heavier, improved performance especially in sequences requiring memory of past observations.
Both models can end up driving in the wrong direction due to the way they have been trained, a reinforcement learning method with score keeping could have performed better.

## Visualisations
|Model||
|:---|:---:|
|CNN|![](https://github.com/PavanKumar-Gudiwada/AutonomousCarRacing/blob/main/CNN_Drive.gif)|
|GRU|![](https://github.com/PavanKumar-Gudiwada/AutonomousCarRacing/blob/main/RNN_Drive.gif)|



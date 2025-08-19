This project was completed as part of my graduate coursework and focuses on building and evaluating deep learning models for autonomous driving in the Gym CarRacing-v0 environment. The work explores both Convolutional Neural Networks (CNNs) for perception from raw images and Recurrent Neural Networks (RNNs/GRUs) for capturing temporal dependencies in driving behavior.

🔹 Project Workflow
1. Data Collection
- Collected driving data by manually controlling the car in the CarRacing-v0 environment.
- Frames and corresponding control actions (steering, acceleration, braking) were logged to create a supervised learning dataset.

2. Model Training
- CNN Model: Trained to predict driving actions directly from pixel inputs.
- RNN/GRU Model: Extended to handle sequential frame information, leveraging temporal context for smoother driving performance.

3. Model Optimization & Evaluation
- Applied post-training quantization to reduce model size and improve inference efficiency.
- Experimented with Quantization-Aware Training (QAT) to mitigate accuracy loss and compared results against the original CNN baseline.

🔹 Key Highlights
- Demonstrates a full ML workflow: data generation → supervised training → optimization → evaluation.
- Evaluates trade-offs between standard CNNs and temporal models (RNN/GRU) in autonomous decision-making.
- Provides comparison between baseline models, quantized models, and QAT models to analyze performance vs efficiency.

🔹 Tech Stack
- Python, PyTorch for deep learning
- OpenAI Gym (CarRacing-v0) for environment simulation
- Numpy and Matplotlib for dataset handling and analysis

# Results & Observations
|Model|Accuracy|Model Size|Inference Time|
|:---|:---:|---:|---:|
|CNN||||
|CNN (quantised)||||
|CNN (quantised)||||
|CNN (QAT)||||
|RNN (GRU)||||

## Visualisations
|Model||
|:---|:---:|
|CNN|![](https://github.com/PavanKumar-Gudiwada/AutonomousCarRacing/blob/main/CNN_Drive.gif)|
|GRU|![](https://github.com/PavanKumar-Gudiwada/AutonomousCarRacing/blob/main/RNN_Drive.gif)|



# Transformer-from-Scratch-Neural-Machine-Translator

This project implements a **Transformer-based sequence-to-sequence model** for English → Kannada translation, fully built **from scratch in PyTorch**, inspired by the paper *Attention Is All You Need*.  

It covers the complete pipeline: model architecture, training on a parallel corpus, inference with autoregressive decoding, and deployment as an interactive Streamlit app for real-time translation.

---

## 🚀 Features
- **Custom Transformer Implementation**  
  - Encoder–decoder architecture with multi-head self-attention and cross-attention  
  - Positional encoding for sequence order
  - Layer Normalization
  - Padding masks and look-ahead masks for sequence handling  
  - Configurable hyperparameters:  
    - `d_model = 512`  
    - `ffn_hidden = 2048`  
    - `num_heads = 8`  
    - `dropout = 0.1`  
    - `max_sequence_length = 200`  

- **Training**  
  - Dataset: **3,00,000 parallel English–Kannada sentence pairs**  
  - Batch size: `30`  
  - Loss: **Cross Entropy Loss** with padding tokens masked  
  - Optimizer: **Adam**  
  - Epochs: **1000+** (long training for convergence)  
  - Training loop with per-batch loss logging and qualitative sample translations  

- **Inference**  
  - **Autoregressive decoding**: model generates Kannada tokens **step by step**, feeding its own predictions back into the decoder  
  - **Greedy decoding** using `torch.argmax` at each step  
  - Dynamic mask creation for handling sequences with start/end tokens  

- **Deployment**  
  - Integrated into a **Streamlit web app** for real-time translation  
  - Users can input English sentences and instantly receive Kannada translations  


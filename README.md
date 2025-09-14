# RISC-V-Edge-AI-Workshop
Repo for development of RISC-V Edge AI Workshop tasks
Multi-Layer Perceptron (MLP) Visualizer

Project Overview

This repository contains my learning and insights from a workshop on neural network visualization. The project involves using a live web-based tool to explore and understand the architecture of a Multi-Layer Perceptron (MLP) model designed for 8x8 pixel image classification. I focused on understanding how a model processes information and the importance of model quantization for embedded systems.

What I Learned

Neural Network Architecture: I gained a hands-on understanding of a Multi-Layer Perceptron (MLP), a foundational neural network model. I learned that the network has a 64-neuron input layer, which corresponds to the 64 pixels of the input image.

Model Visualization: I used a visualizer tool to see a neural network in action. I observed how data flows from the input layer through the hidden layers, with positive activations represented by blue lines and negative activations by orange lines.

Model Quantization: I learned about model quantization, a key concept for embedded machine learning. Quantization is the process of converting a model's weights and activations to lower-precision numbers. This is crucial for deployment on edge devices because it makes models smaller, faster, and more power-efficient.

My Experience with the Tool

I used the visualizer to explore the model's behavior. I successfully loaded a model's weights by pasting the model's content into the tool's interface. I tested the model's predictions by drawing numbers on an 8x8 canvas and observed how the network's connections lit up to make a prediction. I also learned that even a simple model can have incorrect predictions, which highlights the importance of debugging and understanding a network's behavior.

Technologies & Concepts

Model: Multi-Layer Perceptron (MLP)

Concepts: Model Quantization, Neural Network Visualization, Activation Flow

Programming: Python (used for the model training)

Platform: VSD's Neural Network Visualizer

Edge-AI Deployment on RISC-V

<img width="810" height="535" alt="Screenshot 2025-09-15 at 10 44 24 PM" src="https://github.com/user-attachments/assets/3a29b76a-8ba6-43fa-a67d-5edb89d8544f" />


Overview

This project is a culmination of a hands-on workshop on the VSDSquadron PRO board, which features a SiFive FE310-G002 RISC-V SoC. It explores the challenges and methods of deploying memory-efficient Machine Learning (ML) models on highly resource-constrained embedded systems. The primary objective was to master quantization and optimization techniques necessary for this process.

The Challenge: Implementing ML on Edge Hardware

The SiFive FE310-G002's limited SRAM (16 KB) and lack of dedicated DSP/vector hardware make running even modest ML models extremely difficult. My key challenge was to overcome these constraints by developing a heavily quantized model that could successfully run on the SoC. The project demonstrates a complete workflow from model training in Python to deployment on a low-level embedded platform.

Key Learnings & Projects

Understanding Linear Regression: I started by implementing Linear Regression from scratch using Gradient Descent in Python. This foundational project, using a dataset of study hours and exam scores, helped me understand core ML concepts.

Choosing the Right Model for the Edge: I implemented and compared K-Nearest Neighbors (KNN) and Support Vector Machines (SVM) for classification. Through this process, I learned that SVM is a superior choice for edge AI because it requires less memory, has faster inference, and provides better generalization.

Handwritten Digit Recognition (MNIST): The final stage of the workshop involves training a handwritten digit classifier using SVM on the MNIST dataset. This project proves that you can achieve strong accuracy for a complex task without needing a large, deep neural network.

The Technical Process: From Python to Hardware

The workshop teaches you a complete workflow that is highly valued in the industry. I learned how machine learning models, which are developed in Python, can be processed into a format suitable for low-level embedded platforms and ultimately applied in real-world hardware implementations.

Here is the code snippet from the workshop, along with a breakdown of what each part does:

```c
#include <stdio.h>
#include <metal/cpu.h>
#include <metal/led.h>
#include <metal/button.h>
#include <metal/switch.h>

#define RTC_FREQ 32768

#define x1 0.77884104f
#define x2 0.0293919f
#define x3 0.03471025f

#define b 42989.00816508669f

float predict(float inp1, float inp2, float inp3) {
    return x1*inp1 + x2*inp2 + x3*inp3 + b;
}

void print_float(float val) {
    int int_part = (int)val;
    int frac_part = (int)((val - int_part) * 100);  // 2 decimal places
    if (frac_part < 0) frac_part *= -1;
    printf("%d.%02d", int_part, frac_part);
}

int main(void) {
    float rDSpend = 165349.2f; //we give test values to let it predict the results
    float aDSpend = 136897.8f;
    float mKSpend = 471784.1f;
    float profit;
   return 0;
}
 ```
Model to Header File: After training a model in Python, the workshop teaches you to extract its important parameters (like weights and biases) and save them into a .h header file.

Deployment with Freedom Studio: You then learned how this .h file can be included in a C/C++ program in Freedom Studio and deployed to the RISC-V SoC.

My Takeaways & Future Work

This project taught me the entire process of implementing an ML model on edge hardware, from initial Python development and model processing to preparing it for deployment. Presently, I have simulated the project using QEMU because I do not have access to the physical VSDSquadron PRO board. My plan is to implement this project in hardware in the future and work with more complex ML models.

Tech Stack & Datasets

Programming: Python (NumPy, Pandas, Scikit-learn), C/C++

Tools: Google Colab, SiFive Freedom Studio 3.1.1, QEMU



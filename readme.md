# LLM Inference Fine-Tuning

An interactive web-based playground for experimenting with large language model (LLM) inference tuning, built with Google's Generative Language API (Gemini).

## Overview

This project demonstrates the differences between **prompt engineering**, **inference tuning**, and **fine-tuning** through a hands-on interface. The playground allows you to explore how different inference parameters affect model behavior and output quality.

## Key Concepts

- **Prompt Engineering**: What you say to the model (system and user prompts)
- **Inference Tuning**: How random or strict the model behaves (temperature, top-p, top-k, max tokens)
- **Fine-Tuning**: Retraining the model on new domain-specific data

This playground demonstrates inference tuning — not actual model fine-tuning.

## Features

### API Key Setup
- Secure API key validation for Google Gemini API
- Automatic model discovery and loading
- Permission and quota checking

### Model Selection
- Lists all available Gemini models that support text generation
- Fallback to safe default if selected model fails
- Dynamic model loading based on API key

### Response Style Presets
Pre-configured personality styles to quickly switch between different model behaviors:
- **Innovative Thinker**: Creative and open-ended responses (T: 1.2, Top-P: 0.95, Top-K: 40)
- **Factual & Precise**: Accurate and concise outputs (T: 0.2, Top-P: 0.8, Top-K: 20)
- **Funny Kid (8–10)**: Playful and humorous responses (T: 1.3, Top-P: 0.95, Top-K: 50)
- **Product Manager**: Strategic thinking and analysis (T: 0.6, Top-P: 0.9, Top-K: 30)
- **No-Nonsense**: Blunt and strictly factual (T: 0.1, Top-P: 0.7, Top-K: 15)
- **Custom**: Create your own configuration

### Model Controls

Fine-tune model behavior with the following parameters:

- **Temperature** (0.0 - 1.5): Controls randomness
  - 0.0 = Deterministic, precise answers
  - 1.0+ = More creative and varied responses
  
- **Top-P** (0.0 - 1.0): Controls diversity via cumulative probability
  - 0.8-0.9 = Balanced approach
  
- **Top-K** (1 - 100): Restricts output to top K most likely tokens
  - Lower = More focused
  - Higher = More diverse
  
- **Max Tokens** (50 - 2048): Maximum length of generated response

### Interactive Prompting
- **System/Instruction Prompt**: Define the model's role and behavior
- **User Prompt**: Enter your question or request
- Real-time output generation with latency tracking

## Contents

- `LLM Inference Fine Tuning.html` - Interactive web-based playground application

## Getting Started

### Prerequisites
- Google Generative Language API key (get one at https://ai.google.dev/)
- Modern web browser with JavaScript enabled

### Usage

1. Open `LLM Inference Fine Tuning.html` in your web browser
2. Paste your Google Generative Language API key
3. Click "Validate API Key" to verify access and load available models
4. Select a response style preset or customize the model controls
5. Enter your system instruction and user prompt
6. Click "Run Prompt" to generate a response
7. Observe how different parameter settings affect the output quality and style

## How It Works

The playground uses the Google Generative Language API to:
1. Validate API credentials
2. Fetch available Gemini models
3. Send requests with configured parameters
4. Display generated responses with performance metrics

The interface provides real-time synchronization between slider and number inputs for easy parameter adjustment.

## Technical Details

- **API**: Google Generative Language API (Gemini)
- **Language**: HTML5, CSS3, JavaScript (Vanilla)
- **Architecture**: Client-side single-page application
- **Styling**: Dark theme with responsive design

## Learning Outcomes

By experimenting with this playground, you'll understand:
- How temperature affects response randomness
- The impact of top-p and top-k sampling strategies
- How system prompts influence model behavior
- The differences between static fine-tuning and dynamic inference tuning
- Trade-offs between creativity and factuality

## Notes

- API key validation checks if your key can list models; generation may still fail due to quota or permission restrictions
- The application will fall back to a safe default model if the selected model fails
- Real-time latency tracking helps measure API response times

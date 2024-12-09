# On-Device LLM Demo

This repository contains a code example inspired by the LinkedIn post: **[On-Device LLMs: The Future of Private, Personalized AI](#)**. It demonstrates the use of on-device LLMs with Google's [MediaPipe](https://ai.google.dev/edge/mediapipe/solutions/guide).

---

## **Table of Contents**

1. [Introduction](#on-device-llm-demo)
2. [Setup](#setup)
   - [Using Python](#using-python)
   - [Using Node.js](#using-nodejs)
   - [Using PHP](#using-php)
   - [Using Ruby](#using-ruby)
   - [Using Docker](#using-docker)
3. [Supported Models](#supported-models)
4. [Pre-Converted Models](#pre-converted-models)
5. [Prompts](#prompts)
6. [See It in Action](#see-it-in-action)
7. [Notes](#notes)

---

## Setup

To run this project, you need to serve it using a static server. Below are several options based on your environment:

### Using Python

For Python 3:

```bash
python3 -m http.server 8000
```

For Python 2:

```bash
python -m SimpleHTTPServer 8000
```

### Using Node.js

Install the `http-server` package globally:

```bash
npm install -g http-server
```

Run the server:

```bash
http-server
```

### Using PHP

```bash
php -S localhost:8000
```

### Using Ruby

```bash
ruby -run -e httpd . -p 8000
```

### Using Docker

Run the following command to serve the project via Docker:

```bash
docker run --name static-server -v $(pwd):/usr/share/nginx/html:ro -p 8080:80 nginx
```

---

## Supported Models

You can find the list of supported models [here](https://ai.google.dev/edge/mediapipe/solutions/genai/llm_inference/index?_gl#models). These models are compatible with the MediaPipe Task Gen AI API.

---

## Pre-Converted Models

To ensure compatibility with MediaPipe, use pre-converted models. Below are some examples available for download on Kaggle:

- [Gemma2 2B](https://www.kaggle.com/models/google/gemma-2/tfLite/gemma2-2b-it-gpu-int8) (LiteRT 2b-it-gpu-int8)
- [Gemma1.1 2B](https://www.kaggle.com/models/google/gemma/tfLite/gemma-1.1-2b-it-gpu-int4) (LiteRT 2b-it-gpu-int4)
- [Gemma1.1 7B](https://www.kaggle.com/models/google/gemma/tfLite/gemma-1.1-2b-it-gpu-int4) (LiteRT 7b-it-gpu-int8)

> Ensure you select the model variation optimized for your hardware, whether GPU or CPU, based on your system's capabilities.

See the complete list of pre-converted models [here](https://ai.google.dev/edge/mediapipe/solutions/genai/llm_inference/index#pre-converted-models).

---

## **Prompts**

All example prompts can be found in the **`prompts`** directory.  
To achieve the best results, you must structure your input using **Gemma's prompt formatting**, which includes tokens like `<start_of_turn>` and `<end_of_turn>`. Proper formatting ensures optimal inference performance.

---

## See It in Action

Watch this [YouTube video](https://youtu.be/qyqDejEIO5U) for a hands-on demonstration of the project in action.

### Notes

- Make sure to serve the project from the root directory to correctly load assets and dependencies.
- Ensure you select the model variation optimized for your hardware, whether GPU or CPU, based on your system's capabilities.
- Only use models that have been pre-converted for compatibility with MediaPipe and your hardware

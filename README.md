# Segement Anything Model (SAM) in the Browser

This repository contains a demo to run [Segment Anything Model (SAM)](https://github.com/facebookresearch/segment-anything) entirely in the browser. Both the encoder (for generating image embeddings) and the decoder (for mask prediction) run entirely in the browser through [`onnxruntime-web`](https://www.npmjs.com/package/onnxruntime-web).

The demo uses [quantized](https://huggingface.co/docs/optimum/concept_guides/quantization) [ONNX](https://onnx.ai/) models generated through [samexporter](https://github.com/vietanhdev/samexporter). Quantized models are smaller in size and require less resources to run but the quality of output is often lower.

The quantized ONNX model for the encoder is roughly 108MB is size. The decoder is also an ONNX model but not quantized. Generating the embedding for an image takes on avaerage 30 seconds to 1 minute in my tests (might vary depending resources available on your machine). Generating a mask takes less than a second.

## Usage

- The demo is available at https://sunu.github.io/SAM-in-Browser/
- Once you upload an image, it will take a while to download the encoder model and generate embeddings. The `Status` field should show the current status
- Once the embeddings have been generated, click on a point on the image to generate a mask

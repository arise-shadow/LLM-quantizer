
# LLM Quantization Tool

This repository provides tools for quantizing large language models (LLMs) such as Meta's Llama 3.1 8B model. It supports various quantization methods to reduce model size and improve inference efficiency.

## Features
- **Model Loading**: Load pretrained LLMs using Hugging Face Transformers.
- **Quantization Methods**: Supports INT8, FP16, and FP8 quantization.
- **Custom Model Path**: Easily specify the model directory.
- **Testing and Validation**: Includes test scripts to verify functionality.

## Installation

Clone the repository and install dependencies:

```bash
git clone https://github.com/your_username/quantize-llm.git
cd quantize-llm
pip install -r requirements.txt
```

## Usage

To quantize a model, use the following command:

```bash
python src/main.py --model_path ./src/models/llama_3_1_8b --quantize_method int8
```

### Arguments
- `--model_path`: Path to the pretrained model directory.
- `--quantize_method`: Quantization method. Options are:
  - `int8` (default)
  - `fp16`
  - `fp8`

Example:

```bash
python src/main.py --model_path ./src/models/llama_3_1_8b --quantize_method fp16
```

## Project Structure

```plaintext
quantize-llm/
├── README.md
├── requirements.txt
├── src/
│   ├── main.py          # Entry point for quantization
│   ├── quantize.py      # Core quantization logic
│   ├── utils.py         # Utility functions (e.g., logging)
│   └── models/
│       └── llama_3_1_8b/ # Example pretrained model directory
│           ├── config.json
│           ├── tokenizer.json
│           └── pytorch_model.bin
├── tests/
│   ├── test_quantize.py # Tests for quantization
│   └── test_utils.py    # Tests for utility functions
└── examples/
    ├── sample_input.txt # Example input for testing
    └── quantized_output.bin # Example quantized model output
```

## Dependencies

- `torch>=2.0`
- `transformers>=4.31.0`
- `datasets`
- `bitsandbytes`
- `numpy`
- `scipy`

Install all dependencies using:

```bash
pip install -r requirements.txt
```

## Testing

Run tests to verify the quantization process:

```bash
pytest tests/
```

## License

This project is licensed under the MIT License.

## Acknowledgements

Inspired by [Demir's Blog](https://blog.demir.io/quantizing-large-language-models-a-step-by-step-example-with-meta-llama-3-1-8b-instruct-model-ea96955f3fb6).

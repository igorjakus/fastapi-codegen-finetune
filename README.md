# fastapi-codegen-finetune

This project implements code completion for FastAPI framework by fine-tuning the CodeGen-mono-small model.

## Project Overview
The goal is to create a code completion model specifically trained on FastAPI patterns and conventions.
We use CodeGen-mono-small (350M parameters) as our base model and fine-tune it for code completion tasks.

## Data Sources & References

### Primary Sources
- [Long Code Arena: A New Era of Training and Evaluation for Code Large Language Models](https://arxiv.org/abs/2406.11612)
  - Used as reference for benchmarking methodology and evaluation metrics

### Model References
- [CodeGen](https://github.com/salesforce/CodeGen)
  - Base model: CodeGen-mono-small (350M parameters)
  - Original paper: [CodeGen: An Open Large Language Model for Code with Multi-Turn Program Synthesis](https://arxiv.org/abs/2203.13474)

### Framework References
- [FastAPI](https://fastapi.tiangolo.com/)
  - Main project we're using for fine-tuning
  - Source of training data and patterns
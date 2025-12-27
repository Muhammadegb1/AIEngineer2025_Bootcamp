# HuggingFace Transformers - Section 32 Summary

In this section of the AI Engineer Course 2025, we explored HuggingFace Transformers, a leading library for Natural Language Processing (NLP).  

## Key Learnings

- **HuggingFace Overview**  
  HuggingFace is a platform and library providing access to pre-trained AI models, datasets, and demos. Think of it as GitHub for AI models. It allows you to use advanced models without training from scratch or dealing with complex math.

- **Pre-Trained Models & Pipelines**  
  - Use pre-trained models for tasks like sentiment analysis, named entity recognition (NER), and zero-shot classification.  
  - `pipeline` simplifies using models: you input text, and it outputs predictions with minimal code.

- **Tokenizers (Preprocessing)**  
  - Convert text into numbers (input_ids) that models understand.  
  - Key methods:
    - `.tokenize()` → split text into tokens  
    - `.convert_tokens_to_ids()` → tokens → numbers  
    - `.decode()` → numbers → text  
  - Special tokens: `[CLS]` (start), `[SEP]` (end)

- **Models (Inference)**  
  - Models take tokenized input and generate predictions.  
  - PyTorch/TensorFlow integration:
    - `AutoModelForSequenceClassification` → text classification  
    - `with torch.no_grad()` → disables gradients during inference  
    - `logits.argmax().item()` → predicted class index  
    - `model.config.id2label` → map index to label  

- **Saving & Loading Models**  
  - `.save_pretrained(directory)` → save model or tokenizer  
  - `.from_pretrained(directory)` → load model or tokenizer  
  - Useful for transferring models between machines or continuing work without retraining.

- **Tokenizer vs Model**  
  - Tokenizer = preprocessing (text → numbers)  
  - Model = inference (numbers → predictions)

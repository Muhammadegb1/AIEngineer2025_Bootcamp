# HuggingFace Transformers

In this section of the AI Engineer Course 2025, I explored HuggingFace Transformers, a leading library for Natural Language Processing (NLP).

## Key Learnings

### HuggingFace Overview
I learned that HuggingFace is a platform and library providing access to pre-trained AI models, datasets, and demos. I can think of it as GitHub for AI models. It allows me to use advanced models without training from scratch or dealing with complex math.

### Pre-Trained Models & Pipelines
I used pre-trained models for tasks like sentiment analysis, named entity recognition (NER), and zero-shot classification.  
I learned how `pipeline` simplifies using models: I input text, and it outputs predictions with minimal code.

### Tokenizers (Preprocessing)
I learned to convert text into numbers (`input_ids`) that models can understand.  
Key methods I used:
- `.tokenize()` → split text into tokens  
- `.convert_tokens_to_ids()` → convert tokens to numbers  
- `.decode()` → convert numbers back to text  
I also learned about special tokens: `[CLS]` (start), `[SEP]` (end).

### Models (Inference)
I used models to take tokenized input and generate predictions.  
With PyTorch/TensorFlow, I learned to:
- Use `AutoModelForSequenceClassification` for text classification  
- Use `with torch.no_grad()` to disable gradients during inference  
- Get the predicted class index with `logits.argmax().item()`  
- Map the index back to the label using `model.config.id2label`

### Saving & Loading Models
I learned to save and load models and tokenizers using:
- `.save_pretrained(directory)` → save a model or tokenizer  
- `.from_pretrained(directory)` → load a model or tokenizer  
This allows me to transfer models between machines or continue working without retraining.

### Tokenizer vs Model
I understood that:
- Tokenizer = preprocessing (text → numbers)  
- Model = inference (numbers → predictions)

# NLP with HuggingFace Transformers – Section Summary

In this section of the AI Engineer Course 2025, I learned to work with pre-trained transformer models for **Question Answering**.

## Key Learnings

### Question Answering with BERT
- Loaded BERT fine-tuned on SQuAD for QA using `BertForQuestionAnswering` and its tokenizer.
- Encoded questions and context (`encode_plus`) and converted tokens back to text.
- Retrieved start and end logits to extract the answer span.
- Handled subword tokens (like `##`) to produce readable answers.
  
### Building a Simple QA Bot
- Created a FAQ bot that predicts answers from a given context.
- Learned to use segment IDs (`token_type_ids`) to differentiate question vs. context tokens.

---

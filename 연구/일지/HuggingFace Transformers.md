## Type of Pipelines

| Task Category                         | Task Name                                                                                                                                                                                                            |
| ------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Audio**                             | `audio-classification`, `automatic-speech-recognition`, `text-to-audio`, `text-to-speech`, `zero-shot-audio-classification`                                                                                          |
| **Conversational**                    | `conversational`                                                                                                                                                                                                     |
| **Depth Estimation**                  | `depth-estimation`                                                                                                                                                                                                   |
| **Document Processing**               | `document-question-answering`, `table-question-answering`                                                                                                                                                            |
| **Feature Extraction**                | `feature-extraction`                                                                                                                                                                                                 |
| **Image Processing**                  | `image-classification`, `image-feature-extraction`, `image-segmentation`, `image-to-image`, `image-to-text`, `mask-generation`, `object-detection`, `zero-shot-image-classification`, `zero-shot-object-detection`   |
| **Natural Language Processing (NLP)** | `fill-mask`, `ner`, `question-answering`, `sentiment-analysis`, `summarization`, `text-classification`, `text-generation`, `text2text-generation`, `token-classification`, `translation`, `zero-shot-classification` |
| **Video**                             | `video-classification`                                                                                                                                                                                               |
| **Visual Question Answering**         | `visual-question-answering`, `vqa`                                                                                                                                                                                   |
| **Specialized Translation**           | `translation_XX_to_YY`                                                                                                                                                                                               |
## AutoTokenizer 와 AutoModel

In Hugging Face Transformers, a checkpoint typically refers to a saved version of a model during training. It’s a snapshot of the model’s parameters and possibly other related information at a particular point in the training process. Checkpoints are useful for various reasons, including:

1. **Resuming Training:**

- If training is interrupted or needs to be paused, checkpoints allow you to resume training from the last saved state rather than starting from scratch.

2. **Fine-Tuning:**

- When fine-tuning a pre-trained model on a specific task or domain, you might want to save checkpoints at regular intervals. This allows you to choose the best-performing model or continue training if needed.

3. **Model Evaluation:**

- Checkpoints are often used for evaluating models on validation or test sets. You can load a saved checkpoint and evaluate its performance without the need to retrain.

4. **Deployment:**

- In deployment scenarios, you might want to save the final trained model as a checkpoint for later use.
Hugging Face Transformers provides functionalities to save and load checkpoints using the `save_pretrained` and `from_pretrained` methods. For example:
```python
from transformers import AutoModel, AutoTokenizer

#Instantiate model and tokenizer  

model = AutoModel.from_pretrained(‘bert-base-uncased’)  
tokenizer = AutoTokenizer.from_pretrained(‘bert-base-uncased’)

# Save the model and tokenizer  
model.save_pretrained(‘bert_checkpoint’)  
tokenizer.save_pretrained(‘bert_checkpoint’)

# Later, you can load the model from the checkpoint:

loaded_model = AutoModel.from_pretrained(‘bert_checkpoint’)
```

### 습득한 python 문법
#### `df['col'].value_counts(ascending=True)`
#### `df.plot.barh()`
#### `df['col'].str.split().apply(len)`
#### `.map(func)`, `.apply(func)`

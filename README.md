## Requirements

You will need [torch](https://pytorch.org), and [transformers](https://github.com/huggingface/transformers) library to load the models.

```requirements.txt
--extra-index-url=https://download.pytorch.org/whl/cu116
torch==1.12.0
transformers~=4.20.1
```

## Model Loading

Load models under `resources/models` using:

```python
from transformers import T5ForConditionalGeneration

# eg. to load the model trained on text representation of java dataset
model = T5ForConditionalGeneration.from_pretrained('resources/models/codet5-base/text/java')
tokenizer = RobertaTokenizerFast.from_pretrained('Salesforce/codet5-base')
```

For command sequence representation you will also have to add some new tokens to the vocabulary.

```python
tokenizer.add_tokens(['</[DEL]/>', '</[INS]/>', '</[LOC]/>'])
```

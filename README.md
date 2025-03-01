# Machine Translation with mBART50

This project focuses on low-resource machine translation using the `mBART50` model. It translates text from English to Vietnamese and is implemented in Google Colab.

## Features

- Fine-tunes `mBART50` for EN-VI translation
- Uses the `IWSLT’15 English-Vietnamese` dataset
- Evaluates translation quality using `SacreBLEU`
- Implements `beam` search and `greedy` search for inference

## Setup

**1. Open the Notebook**

Run the project in Google Colab by opening: `machine_translation_mbart50.ipynb`

**2. Install Required Libraries**

All dependencies are installed directly in the notebook. Run the installation cell:
```sh
!pip install -q transformers sentencepiece datasets accelerate evaluate sacrebleu
```

**3. Load Dataset**

The project uses `IWSLT’15 English-Vietnamese`. The dataset is loaded in the notebook

**6. Load Pretrained Model**

The `mBART50` model and tokenizer are loaded as follows:
``` sh
model_name = "facebook/mbart-large-50-many-to-many-mmt"
tokenizer = AutoTokenizer.from_pretrained(model_name)
model = AutoModelForSeq2SeqLM.from_pretrained(model_name)
```

**5. Train the Model**

The model is fine-tuned using the Trainer API.

**6. Evaluate Model Performance**

Translation results are evaluated using the `BLEU score` with `SacreBLEU`.

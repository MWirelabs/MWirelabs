# Models Index

This file lists all Hugging Face models published under [MWirelabs](https://huggingface.co/MWirelabs).

---

## KhasiBERT

* **HF page:** [https://huggingface.co/MWirelabs/khasibert](https://huggingface.co/MWirelabs/khasibert)
* **Purpose:** Foundational masked LM for Khasi (classification, NER, etc.)
* **License:** [CC BY-NC 4.0](LICENSES/khasibert_LICENSE.txt)
* **Quick usage:**

```python
from transformers import RobertaForMaskedLM, RobertaTokenizerFast, pipeline

model = RobertaForMaskedLM.from_pretrained("MWirelabs/khasibert")
tokenizer = RobertaTokenizerFast.from_pretrained("MWirelabs/khasibert")

fill = pipeline("fill-mask", model=model, tokenizer=tokenizer)
print(fill("Ka Meghalaya ka <mask> ha ka jingpyrkhat jong ki Khasi."))
```

---

## Kren v1

* **HF page:** [https://huggingface.co/MWirelabs/kren-v1](https://huggingface.co/MWirelabs/kren-v1)
* **Purpose:** Khasi generative LM (causal text generation)
* **License:** [CC BY-NC 4.0](LICENSES/kren-v1_LICENSE)
* **Quick usage:**

```python
from transformers import AutoTokenizer, AutoModelForCausalLM

tokenizer = AutoTokenizer.from_pretrained("MWirelabs/kren-v1")
model = AutoModelForCausalLM.from_pretrained("MWirelabs/kren-v1")

inputs = tokenizer("Ka Khasi ka", return_tensors="pt")
outputs = model.generate(inputs.input_ids, max_length=50)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```

---

## Neodac-mini

* **HF page:** [https://huggingface.co/MWirelabs/neodac-mini](https://huggingface.co/MWirelabs/neodac-mini)
* **Purpose:** Cultural knowledge & QA for Northeast India (English)
* **Base:** google/gemma-3-1b-it
* **License:** Apache-2.0
* **Quick usage:**

```python
from transformers import AutoTokenizer, AutoModelForCausalLM

tokenizer = AutoTokenizer.from_pretrained("MWirelabs/neodac-mini")
model = AutoModelForCausalLM.from_pretrained("MWirelabs/neodac-mini")

inputs = tokenizer("Tell me about a festival in Nagaland.", return_tensors="pt")
outputs = model.generate(inputs.input_ids, max_length=60)
print(tokenizer.decode(outputs[0], skip_special_tokens=True))
```

---

## Khasi ↔ English Semantic Search

* **HF page:** [https://huggingface.co/MWirelabs/khasi-english-semantic-search](https://huggingface.co/MWirelabs/khasi-english-semantic-search)
* **Purpose:** Cross-lingual semantic search, embeddings
* **License:** CC0-1.0
* **Quick usage:**

```python
from sentence_transformers import SentenceTransformer

model = SentenceTransformer("MWirelabs/khasi-english-semantic-search")
embeddings = model.encode(["Khasi sentence", "English sentence"])
print(embeddings)
```

---

## GaroVec

* **HF page:** [https://huggingface.co/MWirelabs/GaroVec](https://huggingface.co/MWirelabs/GaroVec)
* **Purpose:** Embeddings for Garo language (private model)
* **License:** CC BY-SA 4.0 (weights & code); training data private
* **Access:** Currently private; contact [MWirelabs](https://huggingface.co/MWirelabs) for access.

---

## IndataAI Core

* **HF page:** [https://huggingface.co/MWirelabs/indataai-core](https://huggingface.co/MWirelabs/indataai-core)
* **Purpose:** Business intelligence engine for Indian business patterns
* **License:** MIT
* **Quick usage:** See Hugging Face model card for usage details.

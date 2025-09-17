# Datasets Index

This file lists datasets published under [MWirelabs](https://huggingface.co/MWirelabs).

---

## Northeast India — Districts & Villages
- **HF page:** https://huggingface.co/datasets/MWirelabs/Northeast-India-Districts-and-Villages
- **Rows:** ~49,275
- **Fields:** State, District, Village
- **Source:** LGDirectory (Government of India) — cleaned and normalized
- **License:** CC BY 4.0
- **Quick usage:**
```python
from datasets import load_dataset

ds = load_dataset("MWirelabs/Northeast-India-Districts-and-Villages")
print(len(ds["train"]))
print(ds["train"][0])

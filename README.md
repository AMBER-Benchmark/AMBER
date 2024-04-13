# AMBER: An Automated Multi-dimensional Benchmark for Multi-modal  Hallucination Evaluation



## Getting Started

### Installation

**1. spacy** is used for near-synonym judgment
```bash
pip install -U spacy
python -m spacy download en_core_web_lg
```
**2. nltk** is used for objects extraction
```bash
pip install nltk
```

### Image Download

Download the images from this [LINK](https://drive.google.com/file/d/1MaCHgtupcZUjf007anNl4_MV0o4DjXvl/view?usp=sharing).

### Responses Generation
|  json file   | Task or Dimension   | Evaluation args | 
|:-------:|:-------:|:-------:|
|query_all.json| All the tasks and dimensions | a |
|query_generative.json| Generative task | g |
|query_discriminative.json| Discriminative task | d |
|query_discriminative-existence.json| Existence dimension | de |
|query_discriminative-attribute.json| Attribute dimension | da |
|query_discriminative-relation.json| Relation dimension | dr |

For generative task (1 <= id <= 1004), the format of responses is:
```bash
[
	{
		"id": 1,
		"response": "The description of AMBER_1.jpg from MLLM."
	},
	
	......
	
	{
		"id": 1004,
		"response": "The description of AMBER_1004.jpg from MLLM."
	}
]
```

For discriminative task (id >= 1005), the format of responses is:
```bash
[
	{
		"id": 1005,
		"response": "Yes" or "No"
	},
	
	......
	
	{
		"id": 15220,
		"response": "Yes" or "No"
	}
]
```

### Evaluation
```bash
python inference.py --inference_data path/to/your/inference/file --evaluation_type {Evaluation args}
```


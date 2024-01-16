# Applied NLP – Assignment 1  
**Due Date:** Jan 16, 2024  

## Objective  
The goal of this assignment is to obtain, extract, clean, and preprocess text from an online source and generate a structured dataset with linguistic annotations. The assignment uses the FAO article *“World food prices dip in December”* as the source text.  

---

## Tasks  

### 1. Text Acquisition  
- Source: FAO article [World food prices dip in December](https://www.fao.org/newsroom/detail/world-food-prices-dip-in-december/en)  
- Input: Provided as `world-food-prices.html`  
- Extraction: `BeautifulSoup` used to isolate body content with id `Contentplaceholder1_C011_Col00`.  

### 2. Text Cleanup  
- Remove newlines and extra spaces.  
- Ensure sentences end with a period.  
- Handle dates (`06/01/2023`) and special symbols (e.g., ©).  

### 3. Pre-processing (spaCy)  
- Load `en_core_web_sm` pipeline.  
- Apply:  
  - Sentence segmentation  
  - Tokenization  
  - Lemmatization  
  - Part-of-speech tagging  
  - Named Entity Recognition (NER)  

### 4. DataFrame Creation  
- Construct `pandas.DataFrame` with columns:  
  - `sent_id` – sentence index  
  - `token_id` – token index within sentence  
  - `text` – token text  
  - `lemma` – lemma of the token  
  - `pos` – part of speech  
  - `ent` – entity type  

### 5. Custom Tokenizer  
- Customized spaCy tokenizer to split dates (e.g., `06/01/2023`) into separate tokens for day, month, and year.  
- Updated infix rules to capture `/` characters.  

---

## Repository Structure  
```

applied-nlp-assignment-1/
│── README.md
│── requirements.txt
│── .gitignore
│── Assignment1_NLP.ipynb
└── Dataset/
└── world-food-prices.html

```

---

## Setup Instructions  
```bash
cd applied-nlp-assignment-1
pip install -r requirements.txt
python -m spacy download en_core_web_sm
```

---

## References

* spaCy documentation: [https://spacy.io/](https://spacy.io/)
* BeautifulSoup documentation: [https://www.crummy.com/software/BeautifulSoup/](https://www.crummy.com/software/BeautifulSoup/)
* FAO Newsroom: [https://www.fao.org/newsroom/](https://www.fao.org/newsroom/)


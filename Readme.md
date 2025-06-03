
# IndoBERT Sentiment Classifier for Social Media Posts – Universitas XYZ

This model is a fine-tuned IndoBERT transformer for performing sentiment analysis on Indonesian social media text (Twitter) related to university services. It classifies input text into **positive**, **neutral**, or **negative** sentiment categories.

## 🧠 Model Description

The model is built upon [`indobert-base-p2`](https://huggingface.co/indobenchmark/indobert-base-p2), a BERT-based transformer pre-trained on over 220 million Indonesian words. The fine-tuning process was done on 7500 samples containing balanced sentiment labels related to online academic services.

- **Label classes**: Positive, Neutral, Negative
- **Preprocessing**: Case folding, punctuation removal, stopword removal, stemming, tokenization (using IndoBERT tokenizer)

## ✅ Intended Use

- Analyzing Indonesian tweets about universities
- Sentiment-driven dashboards for academic service quality
- NLP applications in education sector

## ⚠️ Limitations

- Domain-specific to university-related sentiment
- May not generalize well to informal or slang-heavy text
- Sarcasm or mixed-sentiment detection is not supported
- Doesn’t handle toxicity or hate speech detection

## 📊 Dataset

- **Source**: Custom crawled tweets via keywords and hashtags (e.g. `#telkomuniversity`, `Universitas XYZ`)
- **Size**: 7500 samples
- **Split**: 70% train, 10% validation, 20% test
- **Labels**: 2500 positive, 2500 neutral, 2500 negative
- **Language**: Indonesian

## ⚙️ Training Procedure

### Hyperparameters

- **Learning rate**: 5e-5  
- **Batch size**: 8  
- **Epochs**: 3  
- **Optimizer**: Adam (β1=0.9, β2=0.999, ε=1e-8)  
- **Scheduler**: Linear  
- **Seed**: 42

### Framework Versions

- Transformers: 4.24.0  
- PyTorch: 1.13.0  
- Tokenizers: 0.13.2  

## 📈 Evaluation Metrics

| Metric    | Score |
|-----------|-------|
| Accuracy  | 89%   |
| F1 Score  | 88%   |
| Precision | 87%   |
| Recall    | 89%   |

![image/png](https://cdn-uploads.huggingface.co/production/uploads/6157d43f013078aa50b55498/pJo7M_qjPoNMyZ6WbfbA4.png)


## 💻 Deployment Context

This model was integrated into [`a Django-based sentiment dashboard application`](https://github.com/ShinyQ/Django_Thesis-Sentiboard-University-Sentiment-App) with:
- A custom Twitter crawler
- Real-time sentiment classification
- Wordclouds and sentiment breakdowns by time period
- Admin tools for filtering, deleting, and exporting data


## 🧪 Functional Testing & UAT

### Functional testing (black-box)

All modules passed 100% of test cases:
- Login  
- Dashboard with filtering  
- Crawler with Twitter API  
- Data management (filter/export/delete)

### UAT with Likert scale (3 users)

| Category           | Average Score |
|--------------------|---------------|
| Usability          | 88%           |
| Information Quality| 82%           |
| Interaction Quality| 91%           |

## 📄 Citation

If you use this model or its components, please cite:
```
@article{wijaya2023indobert,
  author    = {Kurniadi Ahmad Wijaya and Ade Romadhony and Donni Richasdy},
  title     = {Implementasi Model IndoBERT pada Dashboard Sentimen Media Sosial (Studi Kasus Universitas XYZ)},
  journal   = {eProceedings of Engineering},
  volume    = {10},
  number    = {4},
  year      = {2023},
  month     = {September},
  url       = {https://openlibrary.telkomuniversity.ac.id},
}
```
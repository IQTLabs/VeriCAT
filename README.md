# VeriCAT
All of the resources generated during the VeriCAT project for quantifying and visualizing and trust in translation 

## Project overview
Everyone uses machine translation (MT), but the output lacks information to accurately gauge accuracy. There are stark differences in translation quality between individual sentences, language pairs, domains, translation engines, and data sources (e.g. news versus forums). MT quality assessment is intrinsically valuable, and is also the bottleneck to improving MT systems. This repo contains links to a user interface for displaying quality estimation, a dataset for training a model on informal text, and will be updated with a state-of-the-art sentence-level quality prediction model. 

## User Interface
The UI (currently in prototype) displays predicted sentence-level quality and identifies named entities in the source text and translations. The UI prototype is at https://ninalopatina.github.io/VeriCAT-UI/, and the repository is at https://github.com/ninalopatina/VeriCAT-UI. Currently, the UI demo has hard-coded text, and is not functionally linked to the model. This is a future direction.

## Data
We generated English translations via the best performing model for RussianEnglish, Facebook’s FairSEQ pre-trained model. Three translators labeled each translation with a direct assessment score (0–100) for each sentence pair, and we provided links to each source text. The mean score is 68, very low for a high resource language pair. We also preserved paragraphs and comment threads, so that these data could be used for document-level and dialogue quality estimation. The dataset can be found at http://www.statmt.org/wmt20/quality-estimation-task.html and the blog post detailing data-set production at https://gab41.lab41.org/how-good-is-your-translation-our-novel-dataset-can-help-you-find-out-d25f6c50af59. 

## Named Entity Recognition 
Named entities are a source of translation errors that is both common and can be identified with high accuracy. Due to the richness of Russian noun declension, names are translated with inconsistent spelling, and, occasionally, words are translated to names and vice versa. We have attained an F1 score of .95 for the person tag in English (On CoNLL-2003, a classic NER set, and Emerging Entities, a novel challenging dataset), and .93 F1 for the Person tag in Russian, (combining factRuEval and the BSNLP shared task). A full description of the BERT model is at https://gab41.lab41.org/how-to-fine-tune-bert-for-named-entity-recognition-2257b5e5ce7e and repository link can be found at https://github.com/chambliss/Multilingual_NER.

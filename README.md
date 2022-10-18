# Pre-trained-transformers-for-fake-reviews-detection

In this project,pre trained hugging face transformer models have been evaluated against 3 different datasets.Models being used are BERT,ROBERTA and XLNET.

Imbalance techniques used:Weighted Random Sampler compared with Class weight being called in bcewithlogitloss() and crossentropy()
Datasets:YELP Restaurant reviews taken from stonybrook,Open Science Framework Reveiws generated from Amazon products,Deception Opinion Spam Corpus dataset related to chicago hotels.
Models are evaluated using F1,Accuracy, and (Mathew Correlation Coefficient,Precision recall curve used for imbalance yelp dataset)
Performance tuning techniques:Autocast gradscaler,gradient accumulations,data loader using pytorch,pin memory

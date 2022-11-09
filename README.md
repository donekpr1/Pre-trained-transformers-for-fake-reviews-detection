# Pre-trained-transformers-for-fake-reviews-detection

In this project,pre trained hugging face transformer models have been evaluated against 3 different datasets.Models being used are BERT,ROBERTA and XLNET.

Imbalance techniques used:Weighted Random Sampler compared with Class weight being called in bcewithlogitloss() and crossentropy()

Datasets:YELP Restaurant reviews taken from stonybrook,Open Science Framework Reveiws generated from Amazon products,Deception Opinion Spam Corpus dataset related to chicago hotels.

Models are evaluated using F1,Accuracy, and (Mathew Correlation Coefficient,Precision recall curve used for imbalance yelp dataset)

Performance tuning techniques:Autocast gradscaler,gradient accumulations,data loader using pytorch,pin memory.

To understand the application of automatic precision scaling and its benefits,below is the link,
https://docs.nvidia.com/deeplearning/performance/mixed-precision-training/index.html

To understand the application and benefits of gradient accumulation ,below is the link,
https://huggingface.co/docs/accelerate/usage_guides/gradient_accumulation
https://kozodoi.me/python/deep%20learning/pytorch/tutorial/2021/02/19/gradient-accumulation.html

Pin memory is set to true in the dataloader of Pytorch when is called for train and test that helps in automatically put the fetched data tensors in memory ,and thus enables faster data transfer to CUDA-enabled GPU’s.

After applying the performance tuning techniques on the Yelp large dataset,the training execution time for an epoch using single GPU has come down from 9 hours to 3 hours and also further reduced at times to 1.5 hours which depends on network bandwidth.This helped increase the batch size from default 32 to 640.Can be further increased and also the max. token length chosen is 256 which can be further increased to 300 and test it further if required.

This project can be further enhanced in future by incorporating gradient clipping.

Happy learning! :)



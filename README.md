
# Customer Review Classification & Analytics
##### A Master Thesis Project for MiBA program, 2024

Links to repositories: [github]; [huggingface]
Links to final models: 
[aspect model]  |  [repurchase model]  |  [binary polarity model]  |  [multi-class polarity model]

This is a repository containing notebook code for review analytics solution which, through the means of Machine Learning, _predicts review aspect, review polarity (sentiment), and reviewer's repurchase intention._ 


### 1. Demo
Examples of aspect labelling:
![review rated with 3 stars](/demo_review_vis_solid/vis_AXUL79019117227993_rate3_plot.png)
![review rated with 1 star](/demo_review_vis_solid/vis_ADHK02763847289959_rate1_plot.png) 
![review rated with 3 stars](/demo_review_vis_solid/vis_EIPI94329159470821_rate3_plot.png)
The percentage values signify prediction score - the level of model's certainty with the aspect prediction. Colors represent larger aspect categories.

### 2. Models
Models were developed from pretrained [rubert-tiny2] one, fine-tuned to perform 3 classification tasks. Performance results for each of them are presented below:

| Model | Test F1 (macro avg) | # of labels | 
| :-----------: | :-----------: | :-----------: | 
| aspect  | 0.94  | 32  |
| repurchase       | 0.9        | 2       |
| binary polarity       | 0.87        | 2       | 
| multi-class polarity       | 0.34 / 0.43*        | 5       |

_*result after shifting class thresholds_



##### Contents of the repository:
- **models** folder: contains pickle file with the clustering model; all classification models are available at [huggingface];
- **demo_review_vis** folder: contains examples of aspect classification of reviews;
- **requirements.txt**: frozen modules requirements needed for the code to function correctly;
###### Notebooks
- **Common Words + Clustering.ipynb**: text processing functions, aspect clustering (KMeans), identification of common words per aspect and their frequencies
- **Manual_Retraining_Aspect_Classifier.ipynb**: final retraining of aspect classifier
- **Classification Repurchase-GPU.ipynb**: final retraining of repurchase classifier
- **Sentiment_Classifier_Retraining_GPU.ipynb**: final retraining of polarity classifier



[//]: # (These are reference links used in the body of this note and get stripped out when the markdown processor does its job. There is no need to format nicely because it shouldn't be seen. Thanks SO - http://stackoverflow.com/questions/4823468/store-comments-in-markdown-syntax)



   [github]: <https://github.com/lisapavlova/customer_feedback_processing>
   [huggingface]: <https://huggingface.co/laskovey>
   [aspect model]: <https://huggingface.co/laskovey/review_train5>
[repurchase model]: <https://huggingface.co/laskovey/repurchase_train6>
[binary polarity model]: <https://huggingface.co/laskovey/polarity_train2>
   [multi-class polarity model]: <https://huggingface.co/laskovey/polarity_train5>
   [rubert-tiny2]: <https://huggingface.co/cointegrated/rubert-tiny2>
   

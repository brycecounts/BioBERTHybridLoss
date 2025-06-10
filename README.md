**Overview** <div>
Biomedical event classification presents unique challenges due to class imbalance and semantic overlap between event types. This project introduces a hybrid loss function that combines focal loss with Sinkhorn divergence to fine-tune a BioBERT-based classifier for biomedical events. We target three biologically significant processes: phosphorylation, activation, and inhibition. Our model is trained on the BioNLP GENIA 2013 dataset and demonstrates improved performance particularly on underrepresented classes by integrating domain-specific knowledge directly into the training process via a biologically informed cost matrix.


<p align="center">
  <img src="figures/Picture1.png" alt="Workflow Diagram" width="700"/>
</p>

**Features** <div> 
Hybrid Loss Function: Combines focal loss and Sinkhorn distance to mitigate class imbalance while encoding domain-specific structure via a biologically informed cost matrix.

BioBERT Fine-Tuning: Custom fine-tuning on BioBERT on the BioNLP GENIA 2013 dataset for event extraction tasks involving activation, inhibition and phosphorylation.

Mechanistically Informed Cost Matrix: Introduces biological priors into the loss function, penalizing misclassifications based on mechanistic distances between event types.

Synonym Augmentation: Implements WordNet synonym augmentation to improve trainign distribution balance for minority classes. 

Training Optimization: Includes cosine annealing scheduler, early stopping, and class-weighting via the effective number of samples. 

Eval Metrics and Visuals: Includes precision, recall, F1-score, and visualizations of training performance, confusion matrices, and class-specific improvements. 




**Project Structure** <div>
BioBERTHybridLoss/ <div>
├── data/ <div>
├── figures/ <div>
├── notebook/ <div>
├── README.md <div>
└── requirements.txt

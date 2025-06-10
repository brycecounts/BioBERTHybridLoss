Overview <div>
Biomedical event classification presents unique challenges due to class imbalance and semantic overlap between event types. This project introduces a hybrid loss function that combines focal loss with Sinkhorn divergence to fine-tune a BioBERT-based classifier for biomedical events. We target three biologically significant processes: phosphorylation, activation, and inhibition. Our model is trained on the BioNLP GENIA 2013 dataset and demonstrates improved performance particularly on underrepresented classes by integrating domain-specific knowledge directly into the training process via a biologically informed cost matrix.

<p align="center">
  <img src="figures/Picture1.png" alt="Workflow Diagram" width="700"/>
</p>
Features <div>
Hybrid Loss Function: Combines focal loss and Sinkhorn distance to mitigate class imbalance while encoding domain-specific structure via a biologically informed cost matrix.
<br>
BioBERT Fine-Tuning: Custom fine-tuning on BioBERT on the BioNLP GENIA 2013 dataset for event extraction tasks involving activation, inhibition and phosphorylation. Only the final two layers of BioBERT are updated, preserving pretrained biomedical semantics.
<br>
Mechanistically Informed Cost Matrix: Encodes biological relationships between event types—e.g., phosphorylation is biologically more distant from inhibition than from activation—into the loss function.
<br>
Synonym Augmentation: Applies targeted synonym replacement using WordNet to enrich underrepresented event classes in the training set.
<br>
Training Optimization: Incorporates early stopping, cosine annealing learning rate schedule, and class re-weighting using the effective number of samples for stable convergence and improved generalization.
<br>
Eval Metrics and Visuals: Includes detailed evaluation (precision, recall, F1-score) and visualizations of learning curves, confusion matrices, and per-class improvements.

Project Structure <div>
BioBERTHybridLoss/ <div>
├── data/ <div>
├── figures/ <div>
├── notebook/ <div>
├── README.md <div>
└── requirements.txt

Installation <div>

Clone the repository and install dependencies:

bash
Copy
Edit
git clone https://github.com/yourusername/BioBERTHybridLoss.git
cd BioBERTHybridLoss
pip install -r requirements.txt
Running the Model <div>

To run training with hybrid loss:

bash
Copy
Edit
python train.py --loss hybrid --lambda 1
To run the baseline (focal loss only):

bash
Copy
Edit
python train.py --loss focal
To evaluate:

bash
Copy
Edit
python evaluate.py --model checkpoints/best_model.pt
Dataset <div>
We use the BioNLP Shared Task GENIA 2013 dataset (preprocessed via BigBio). Only the three target event types are used:

Phosphorylation (label 2)

Activation (label 1)

Inhibition (label 0)

Citation <div>

Counts, B., Azam, M., Xu, D., et al. Hybrid Loss Functions and LLMs: Towards Smarter Biomedical Event Extraction with BioBERT. University of Missouri, 2025.

Acknowledgements <div>
We thank the Digital Biology Lab at the University of Missouri for critical feedback and support.

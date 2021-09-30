# IHS-H2-Bioinformatics-Drug-Target

This project is for the IEEE Covid-19 data hackathon's H2: Bioinformatics Drug Challenge. 

Our final method is an feed-forward neural network model to predict docking scores of candidate drug molecules on SARS-CoV-2 protein targets.  We also tried XGBoost regressor and other , but their performance in MAE are higher compared with NN model.  

In the repository, `src` file contains all of our codes and `BestNN_circ` file contains our pretrained NN models.

### In `src`:

- `FineTuneXGB.ipynb`: finetune 3 main parameters of XGBoost regressor(baseline) on each protein target including the number of the estimators, the depth of the tree and the minimum child weight.
- `FingerprintsGeneration.ipynb` : generate 4 types of fingerprints(MACCS fingerprint, RDKit fingerprint, ECFP4 and MHFP6) and get their UMAP visualization.
- `NN_RandomSearch.ipynb`: apply random search for tuning our feed-forward neural network's hyper-parameters including layer depth, layer width and dropout rate.
- `NN_arch.pk`: saved best neural network architecture from random search.  
- `TestPredcition.ipynb`: use our pretrained model to get docking score prediction on test set.

### In `BestNN_circ`:

- bestNN_circ_col{x}: saved neural network model pretrained on training set for the protein target in column x (x ranges from 0 to 17). The model use the  architecture in `src/NN_arch.pk`.

# RSNA 2024 Lumbar Spine Degenerative Classification

## To-dos:
- [x] Create a dataset class to load images into batches
- [x] Assign a floating point number to each label (soft labels)
- [x] Choose a model: EfficientNet
- [x] Set up tensorboard for training
- [x] Set up a training pipeline for each orientation (currently only Sagittal T2 is set up, need to set up remaining)
- [ ] Set up a LR scheduler
- [ ] Better pretrained models? DINO? 
- [ ] Try different loss functions
- [ ] Play with the contrast values of the scans? adaptive instance norm or hist matching similar
- [ ] Mitigation on certrain label sequences that have very little samples?


## Current Status:
- Data pipeline is set up
- Model training can  be started
- Using EfficientNet B7 pretrained on small ImageNet
- Potential problems
    - model choice? unfreezing choices?
    - loss choice? didnt add weighting factor to moderate and severe? (MSE,BCELoss)
    - learning rate too low? (try LR scheduling next)
    - accuracy doesnt reflect model performance? use precision and recall as well?
    - should we split all diagnosis into 2 types?
        - how to deal with certain label combinations that have very little samples

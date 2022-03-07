# Flower_Classification_on_TPU-kaggle-
practice competition in kaggle that uses TPU for training

- Applying TPU and readin files are simply followed https://www.kaggle.com/ryanholbrook/create-your-first-submission

2022/March/4 - version 1
- Use 'EFficientNetB4' and add FC layer at the end (+ add dropout for regularization)
- 40 epochs, adam optimizer, learning rate with expoential decay
- data augmentation: flip(horizontal, vertical), brightness
- accuracy: test - 95%, val - 90%, test - 88% (kaggle score)

suggestion: maybe need to run more epochs. add more data augmentation, learn how to do fine-tuning. 

2022/March/8 - version 2
- Erased all FC layers and simply add classifer at the end
- Found out `tf.keras.applications.EfficientNet` contains `rescaling layer` at the very front of the model, 
  causing double normalization, which makes the values of images very very small
  As a solution, I could either delete normalization during data loading, or import `efficientnet.tfkeras.EfficientNet`, which does not have `rescaling layer`
  
- Used 'EfficientNetB0' to increase training speed
- data augmentation: horizontal flip, brightness, saturation
- 30 epochs, accuracy: test - 99%, val - 94%, test - 93% (kaggle score)

suggestion: should try 'EfficientNetB7', try more regularization, try model ensemble


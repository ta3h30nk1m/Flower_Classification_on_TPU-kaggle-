# Flower_Classification_on_TPU-kaggle-
practice competition in kaggle that uses TPU for training

- Applying TPU and readin files are simply followed https://www.kaggle.com/ryanholbrook/create-your-first-submission

2022/March/4 - version 1
- Use 'EFficientNetB4' and add FC layer at the end (+ add dropout for regularization)
- 40 epochs, adam optimizer, learning rate with expoential decay
- data augmentation: flip(horizontal, vertical), brightness
- accuracy: test - 95%, val - 90%, test - ?

suggestion: maybe need to run more epochs. add more data augmentation, learn how to do fine-tuning. 

**Modified version of original Att-GAN, for custmozied training facial attributes and Fair-face dataset.**

# How to Run


1. Put the the training data folder into the `data` folder, Att-GAN requires training and validation data separately.
2. Put the training & validation labels into the training folders. For fairface labels are there already.
3. Run training/testing commands



## Example Usage for Fairface Dataset:

### Training:

```bash
python train.py \
--img_dir ./data/FairFace_new/ \
--train_label_path ./labels/FairFace_new/train_label.txt \
--val_label_path ./labels/FairFace_new/val_label.txt  \
--load_size 224 \ # Image original size
--crop_size 224 \ # Image cropped/input size (better to be the same as load_size)
--n_epochs 500 \ # Number of iterations, larger takes longer time
--epoch_start_decay 100 \
--model model_128 \ # model of the output image dimension, should be smaller than crop_size
--experiment_name AttGAN_128_FairFace \ # folder name for the data
--batch_size 32
```

### Testing:

#### Testing inverting attribute 1 at a time (test data uses CAM2 Crowdsourcing team member):

```bash
python test.py \
                                                   --experiment_name AttGAN_128_FairFace \
                                                   --img_dir ./test/data \
                                                   --test_label_path ./test/test_labels_f.txt
```



Refer to `README.md` for more testing commands details
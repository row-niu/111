We train a ResNet-56 and iteratively slim it into 13/16, 11/16 and 5/8 of the original width.

1. Enter this directory.

2. Make a soft link to your CIFAR-10 directory. If the dataset is not found in the directory, it will be automatically downloaded.
```
ln -s YOUR_PATH_TO_CIFAR cifar10_data
```

3. Set the environment variables.
```
export PYTHONPATH=.
export CUDA_VISIBLE_DEVICES=0
```

4. Run CSMF to train a base ResNet-56.
```
python csmf/do_csmf.py -a src56 -i 0
python csmf/do_csmf.py -a src56 -i 1
python csmf/do_csmf.py -a src56 -i 2
```
5. Start with a pre-trained model, for example src56_train file is a pre-trained model

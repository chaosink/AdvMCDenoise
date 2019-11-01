# Instructions to use the code.

This code relies a lot on the projects GauGAN, SRGAN, BasicSR,pix2pix. Credit to these pytorch projects.
Also credits to Disney KPCN project.


# model weights
**weights** dir can be downloaded from [googledrive](https://drive.google.com/open?id=1ql_ti30l4UUcLv3W_ooAp1WXpR5ibJZC)
We provide two set of model weights. 
"./experiment/kjl/models/opt_XX.pth" is trained from KJL large indoor room datasets without seperating Specular and Diffuse components. You can finetune the weigths to your own dataset based on this pretrained weights.

"./experiments/tungsten_diffuse/models/opt_XX.pth" and "./experiments/tungsten_specular/models/opt_XX.pth" is trained on Disney KPCN datasets. details can be seen ...





# data
**data** dir can be downloaded from [googledrive](https://www.google.com)

This directory provides sample data from some scenes on Tungsten scenes.
This directory also provides the utility scripts to do data processing, for example, to process EXR files, Tungsten data pre-processing ect..


# runscripts
**script** dir contains json files for training/testing  

**Attention!!!   Change the settings in json files to include your own data path and project root
Specifically, remember to change the "dataroot_NOISY" "dataroot_GT" "root" "val_root" to your paths**


## to run 

#### training

```
python train_diffuse.py -opt script/train/train_seperate_denoiser_diffuse.json
```

```
python train_specular.py -opt script/train/train_seperate_denoiser_specular.json
```

#### testing

```
python test_diffuse.py -opt script/test/test_seperate_denoiser_diffuse.json
```


```
python test_specular.py -opt script/test/test_seperate_denoiser_specular.json
```

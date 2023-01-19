# Learning_to_diversify
This is the modified code repository for ICCV2021 'Learning to Diversify for Single Domain Generalization'. 

All Rights reserved to the original authors: https://github.com/BUserName/Learning_to_diversify
Paper Link: http://arxiv.org/abs/2108.11726

## Update: Single DG with Resnet-18
Recently, we receive increasing enquiry about single DG on PACS with Resnet-18 Backbone. (In the paper, we reported Alexnet result)
Please try hyperparameters lr=0.002 and e=50, to start your experiment. 

We report the following single DG result on PACS, with resnet-18 as the backbone network:
[TODO]
L2D(AlexNet, Paper) & 56.26 & 51.04 & 58.42 & 55.24\\
L2D(Resnet18) &  68.41 & 43.56 & 48.84 & 53.60\\
L2D(Resnet18+MDAR$) &  57.57 & 50.09 & 65.51 & 57.72\\

## Quick start: (Generalizing from photo domain to Rest(A,C,S) with ResNet-18)
1. Install the required packages.
2. Download PACS dataset.
3. Execute the following code.
```
bash run_main_PACS_sdg.sh
```

## Change dataset
In line 266-300 of train.py, we provide 3 different datasets settings (PACS, VLCS, OFFICE-HOME).
You can simply uncomment it to start your own experiment. It may require hyper-parameter fine tuning for some of the tasks.

## Modified Part
We add Multi domain alignment with redundancy reduction for the sDG task. We observe significant increase in the sketch domain.
-Download PACS dataset and save in this level as a separate folder named 'PACS'.

# Learning_to_diversify
This is the modified code repository for ICCV2021 'Learning to Diversify for Single Domain Generalization'. 
We test effectiveness of our proposed disentanglement loss MDAR (Multi Domain Alignment with redundancy reduction)

All Rights reserved to the original authors: https://github.com/BUserName/Learning_to_diversify

Paper Link: http://arxiv.org/abs/2108.11726

## Update: Single DG with Resnet-18

Please try hyperparameters lr=0.002 and e=50, to start your experiment. 

We report the following single DG result on PACS, with resnet-18 as the backbone network:
[TODO]

| Model                | A     | C     | S     | Avg.  |
|----------------------|-------|-------|-------|-------|
| L2D(AlexNet, Paper)  | 56.26 | 51.04 | 58.42 | 55.24 |
| L2D(Resnet18)        | 68.41 | 43.56 | 48.84 | 53.60 |
| L2D(Resnet18+L_MDAR) | 57.57 | 50.09 | 65.51 | 57.72 |

## Quick start: (Generalizing from photo domain to Rest(A,C,S) with ResNet-18)
1. Install the required packages.
2. Download PACS dataset. (We used the official dataset introduced in Li et al. "Deeper, Broader and Artier Domain Generalization")
3. Run the following code.
```
sh run_main_PACS_sdg.sh
```

## Change dataset
In line 266-300 of train.py, we provide 3 different datasets settings (PACS, VLCS, OFFICE-HOME).
You can simply uncomment it to start your own experiment. It may require hyper-parameter fine tuning for some of the tasks.

## Modified Part
We add MDAR (Multi Domain Alignment with Redundancy reduction) for the sDG task. We observe significant increase in the sketch domain.
-Download PACS dataset and save in this level as a separate folder named 'PACS'.

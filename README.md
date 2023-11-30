# CRAFT-train
On the official CRAFT github, there are many people who want to train CRAFT models. 

However, the training code is not published in the official CRAFT repository. 

There are other reproduced codes, but there is a gap between their performance and performance reported in the original paper. (https://arxiv.org/pdf/1904.01941.pdf) 

The trained model with this code recorded a level of performance similar to that of the original paper.

```bash
├── config
│   ├── syn_train.yaml
│   ├── ic15_train.yaml
├── data
│   ├── pseudo_label
│   │   ├── make_charbox.py
│   │   └── watershed.py
│   ├── boxEnlarge.py
│   ├── dataset.py
│   ├── gaussian.py
│   ├── imgaug.py
│   ├── imgproc.py
├── loss
│   └── mseloss.py
├── metrics
│   └── eval_det_iou.py
├── model
│   ├── craft.py
│   └── vgg16_bn.py
├── utils
│   ├── craft_utils.py
│   ├── inference_boxes.py
│   └── utils.py
├── trainSynth.py
├── trainIC15.py
└── eval.py
```

### Training

1. Write configuration in yaml format
2. Put the yaml file in the config folder
3. Run train code (trainSynth.py or trainIC15.py)
4. Then, experiment results will be saved to ```./exp/[yaml]``` by default.

```
CUDA_VISIBLE_DEVICES=0,1 python3 trainSynth.py --yaml=syn_train   # run supervision code
CUDA_VISIBLE_DEVICES=0,1 python3 trainIC15.py --yaml=ic15_train   # run weak-supervision code
```

### Arguments
* ```--yaml``` : configuration file name

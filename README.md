# Abstract

Это репозиторий для разбора статьи Learning-Rate-Free Learning by D-Adaptation. В статье проведены следующие эксперименты.

## Logistic regression

Method: ```Adam```

Model: Logistic regression

Datasets:
 - Sensorless
 - Aloi
 - DNA
 - Glass
 - Iris
 - Letter
 - Pendigits
 - smallNORB
 - USPS
 - Vehicle
 - Vowel
 - Vine

Source: [LIBSVM](https://www.csie.ntu.edu.tw/~cjlin/libsvmtools/datasets/)

Обучение длилось 100 эпох.

На 60, 80 и 95 эпохах скорость обучения уменьшалась в 10 раз.

Для Adam скорость обучения была подобрана линейным поиском.

Во всех случаях ```D-Adapt Adam``` дает не худшую точность или лучшую точность до $5\%$, чем ```Adam```.

## Image classification

Method: ```SGD```

Models (corresponding to datasets):
 - WRN-16-8
 - DenseNet
 - ResNet-50

Datasets:
 - CIFAR10
 - CIFAR100
 - ImageNet 2012

Sources:
 - [CIFAR](https://www.cs.toronto.edu/~kriz/cifar.html)
 - [ILSVRC](https://image-net.org/challenges/LSVRC/index.php)

Во всех случаях ```D-Adapt SGD``` показал не худшую точность, чем ```SGD```.

## Natural language processing

Method: ```Adam```

Models (corresponding to datasets):
 - LSTM
 - RoBERTa
 - GPT Transformer

Datasets:
 - IWSLT14
 - BookWiki
 - Bookwiki

Sources: **NA**

Во всех случаях ```D-Adapt Adam``` получил сопоставимый коэффициент неопределенности с ```Adam```.

## Further experiments

Method: ```SGD``` for COCO and ```Adam``` for others

Models (corresponding to datasets):
 - vit_tiny_patch16_224
 - Faster-RCNN with pretrained ResNeXt-101-32x8d
 - VarNet 2.0
 - DLRM

Datasets:
 - ImageNet 2012
 - COCO 2017
 - fastMRI Knee
 - Criteo Kaggle

Sources:
 - [ILSVRC](https://image-net.org/challenges/LSVRC/index.php)
 - [COCO](https://cocodataset.org/#download)
 - [fastMRI](https://fastmri.med.nyu.edu/)
 - [Criteo Kaggle](https://www.kaggle.com/datasets/mrkmakr/criteo-dataset)

vit_tiny_patch16_224 обучилась с помощью ```D-Adapt Adam``` на ImageNet хуже, чем с помощью ```Adam```.

В остальных случаях адаптированные методы показали сопоставимое качество обучения.

# Источники

 - Публикация статьи: [ArXiv](https://arxiv.org/abs/2301.07733)
 - Текст статьи: [Pdf](Learning-Rate-Free%20Learning%20by%20D-Adaptation%20Aaron%20Defazio%2C%20Konstantin%20Mishenko.pdf)
 - Код, предоставленный в статье: [GitHub](https://github.com/facebookresearch/dadaptation)


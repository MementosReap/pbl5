# Prepare Datasets (For a simple run, Just install the DAVIS datasets, it should have enough datasets for presentation :v )

**Important:** This guide is designed for users operating on a Unix-like system such as Linux or MacOS. 

In this section, we'll walk you through the process of preparing the datasets required to conduct our experiments. For semi-supervised Video Object Segmentation (VOS), the following datasets are needed: [DAVIS 2016](#davis-2016), [DAVIS 2017](#davis-2017). For Video Instance Segmentation (VIS) experiments, the [UVOv1.0](#uvo-v10) dataset will be utilized.

To begin, create a directory named `data` at the root of your project. This is where all the datasets will be stored:

```bash
mkdir -p data
```

If these datasets are already downloaded and available on your machine, you can create soft links to link the existing data to the structure we expect to find it in. For clarity, we will show you the required directory structures below using the `tree` command.


## Preliminary Checks

Before proceeding to download and process the datasets, it is essential to verify that your machine has sufficient disk space. You can use the `df -h` command in the terminal to check. After unpacking and discarding all compressed archives, the final disk space usage for the datasets we use is approximately:

```txt
 1.9G   data/DAVIS/2016
 7.3G   data/DAVIS/2017
 6.3G   data/YouTube2018
  26G   data/mose
 7.9G   data/bdd100k
 1.4T   data/UVOv1.0
```

Now that the preliminary checks are complete, we can move on to preparing each individual dataset. Please note that you are not required to download all the datasets that we have mentioned. Instead, you can selectively follow the instructions for the datasets you wish to download. Furthermore, we do not necessarily download and prepare all subsets of a dataset, but rather the ones we used in our experiments.

## DAVIS 2016

You can download the DAVIS 2016 dataset from their [official website](https://davischallenge.org/davis2016/code.html). For example, use the following commands to download and extract the dataset:

```bash
mkdir -p data/DAVIS
cd data/DAVIS

wget https://graphics.ethz.ch/Downloads/Data/Davis/DAVIS-data.zip
unzip DAVIS-data.zip
mv DAVIS 2016 # Rename DAVIS to 2016

cd -
```

The directory structure of the DAVIS 2016 dataset should look like this:

```txt
data/DAVIS/2016
├── Annotations
│   ├── 1080p
│   ├── 480p
│   └── db_info.yml
├── ImageSets
│   ├── 1080p
│   └── 480p
├── JPEGImages
│   ├── 1080p
│   └── 480p
└── README.md
```

## DAVIS 2017

Similar to the DAVIS 2016 dataset, you can download the DAVIS 2017 dataset from their [official website](https://davischallenge.org/davis2017/code.html). The following commands will download, extract, and organize the data:

```bash
mkdir -p data/DAVIS/2017
cd data/DAVIS

# DAVIS 2017 Train and DAVIS 2017 Validation
wget https://data.vision.ee.ethz.ch/csergi/share/davis/DAVIS-2017-trainval-480p.zip
wget https://data.vision.ee.ethz.ch/csergi/share/davis/DAVIS-2017-trainval-Full-Resolution.zip
unzip DAVIS-2017-trainval-480p.zip
unzip -o DAVIS-2017-trainval-Full-Resolution.zip
mv DAVIS 2017/trainval # Move and rename DAVIS to 2017/trainval
rm DAVIS-2017-trainval-480p.zip
rm DAVIS-2017-trainval-Full-Resolution.zip

# DAVIS 2017 Test-dev
wget https://data.vision.ee.ethz.ch/csergi/share/davis/DAVIS-2017-test-dev-480p.zip
wget https://data.vision.ee.ethz.ch/csergi/share/davis/DAVIS-2017-test-dev-Full-Resolution.zip
unzip DAVIS-2017-test-dev-480p.zip
unzip -o DAVIS-2017-test-dev-Full-Resolution.zip
mv DAVIS 2017/test-dev # Move and rename DAVIS to 2017/test-dev
rm DAVIS-2017-test-dev-480p.zip
rm DAVIS-2017-test-dev-Full-Resolution.zip

cd -
```

The directory structure of the DAVIS 2017 dataset should look like this:

```txt
data/DAVIS/2017
├── test-dev
│   ├── Annotations
│   │   ├── 480p
│   │   └── Full-Resolution
│   ├── DAVIS
│   │   ├── Annotations
│   │   ├── ImageSets
│   │   ├── JPEGImages
│   │   ├── README.md
│   │   └── SOURCES.md
│   ├── ImageSets
│   │   ├── 2016
│   │   └── 2017
│   ├── JPEGImages
│   │   ├── 480p
│   │   └── Full-Resolution
│   ├── README.md
│   └── SOURCES.md
└── trainval
    ├── Annotations
    │   ├── 480p
    │   └── Full-Resolution
    ├── ImageSets
    │   ├── 2016
    │   └── 2017
    ├── JPEGImages
    │   ├── 480p
    │   └── Full-Resolution
    ├── README.md
    └── SOURCES.md
```


## What's Next?

Now that you have prepared the datasets, you can [prepare the checkpoints](03-prepare-checkpoints.md) that are necessary for [running our VOS and VIS experiments](04-running-experiments.md).

# StarData

## Installing TorchCraft

Note: The current set of replays are only compatible with the 1.3.0 version of torchcraft included here.

Simply do 

```
git submodule update --init
cd TorchCraft
pip install .
```

## Downloading the Data

You can find the replays in an AWS S3 bucket at s3://stardata
- s3://stardata/dumped_replays contains the replays in a format readable by TorchCraft
- s3://stardata/battles are text files, containing one battle each. Each battle is 3 lines:
  - xmin, xmax, ymin, ymax, tmin, tmax: the bounding rectangle for the battle. Multiply time by 3 to get real frame count, or don't to index directly into the dumped datasets.
  - Type and number of units on team 1
  - Type and number of units on team 2
- s3://stardata/original_replays.tar contains the original replays.

## Reproducing Results

Some of the reproduction scripts are included, others scripts will be added as 
soon as we clean up the code and make it easy to install/run. Simply `make` and
you're good to go. All cpp files can be run like `script /path/to/replays/**/*.rep`

- extract_stats tells you some stats about the replays
- extract_units preprocesses for battle clustering
- get_corrupt_replays tells you what replays are considered corrupt
- cluster.py can be run on the output of extract_units to do battle clustering.

## Attributions

The white paper for the dataset is at:

Lin, Z., G., Jonas, K., Vasil, Synnaeve, G., AIIDE 2017. _STARDATA: A StarCraft AI Research Dataset_

We attribute most of the replays to [bwrep](http://bwreplays.com/) and [G. Synnaeve, P. Bessiere, A Dataset for StarCraft AI & an Example of Armies Clustering, 2012.](https://arxiv.org/pdf/1211.4552.pdf)
Please see the paper for a complete list of references.

## License

StarData is BSD-licensed. We also provide an additional patent grant.
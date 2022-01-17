opencropmaps
================

This site provides links to view and obtain agricultural maps and
groundtruth data developed under the project *Creating Open Agricultural
Maps and Groundtruth Data to Better Deliver Farm Extension Services*,
funded by Tetra Tech for [Enabling Crop Analytics at
Scale](https://cropanalytics.net).

## Datasets

There are two types of data currently available:

1.  Label data: Polygons collected by Farmerline’s GPS-enabled Mergdata
    platform describing the boundaries around crop fields and the
    primary, secondary, and tertiary crops growing in them.

2.  Maps of predicted crop types: Maps generated using Random Forests
    model trained using the label data and predictors drawn from
    Sentinel-1, Sentinel-2, and PlanetScope data.

## Accessing data

### From S3

These datasets can be downloaded from this bucket by AWS account
holders. Data are stored under the following prefixes:

-   labels/
-   maps/

These can be viewed using the AWS command line interface (CLI):

``` bash
aws s3 ls s3://opencropmaps/ --request-payer
```

    PRE labels/
    PRE maps/

To download a dataset, here’s an example command:

``` bash
aws s3 cp \
s3://opencropmaps/maps/croptypes/ghana/2020/ejura_tain_2020_2yr_4class.tif \
~/Desktop/ --request-payer
```

    download: s3://opencropmaps/maps/croptypes/ghana/2020/ejura_tain_2020_2yr_4class.tif to ../../../Desktop/ejura_tain_2020_2yr_4class.tif

That will download a map of prediced crop types for Ejura-Tain for the
year 2020 to your desktop (you might need to replace \~/ with the full
path to your home directory).

### From Box

The data may also be downloaded from a [public Box
folder](https://airg.box.com/s/s9vhe5zy39e7oljc233n4bc3fxcow5fe).

## Viewing data

An example of how to view the data (using a jupyter notebook) is
available [here](notebooks/croptype_viewer.ipynb).

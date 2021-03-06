# Densecap-tensorflow

## NOTE
* The scripts should be compatible with both python 2.X and 3.X. Although I built it under python 2.7.

## TODO:

- [x] preprocessing dataset.
- [x] roi_data_layer & get data well prepared for feeding.
- [x] proposal layer
- [x] sentense data layer
- [x] embedding layer
- [x] get loc loss and caption loss
- [ ] overfit a mini-batch
- [ ] context fusion


## Dependencies

```commandline
pip install -r lib/requirements.txt
```

**For evaluation, one also need:**  
* java 1.8.0
* python 2.7(according to [coco-caption](https://github.com/tylin/coco-caption)

To install java runtime by:  
```commandline
sudo apt-get install openjdk-8-jre
```

## Preparing data

* Firstly, check `lib/config.py` for `LIMIT_RAM` option. If one has RAM `less than 16G`, I recommend 
setting `__C.LIMIT_RAM = True`(default True).
    * If `LIMIT_RAM = True`, setting up the data path in `info/read_regions.py` accordingly, and run 
    the script with python. Then it will dump 
    `regions` in `REGION_JSON` directory. It will take time to process more than 100k images, so be patient.
    * In `lib/preprocess.py`, set up data path accordingly. After running the file, it will dump `gt_regions` of
    every image respectively to `OUTPUT_DIR` as `directory` or just a big `json` file.

# Audio Steganography
A python script to hide information over an audio file in .wav format

## Overview
 - The script wav-steg.py can be used to hide and recover data too. The input and output filenames are all configurable through command line inputs
```
$ python wav-steg.py --help
    Usage options:
     -h, --hide     If present, the script runs to hide data
     -r, --recover  If present, the script runs to recover data
     -s, --sound    What follows is the name of carrier wav file
     -d, --data     What follows is the file name having data to hide
     -o, --output   Output filename of choice
     -n, --nlsb     Number of LSBs to use
     -b, --bytes    Number of bytes to recover
     --help         Display help
```
 - Secret to be known to recover data from the steganographic output is the number of LSBs used and the number of bytes hidden.

## Hide data
```
python wav-steg.py -h -d data.txt -s opera.wav -o opera_steg.wav -n 2
```

## Recover data
```
python wav-steg.py -r -s opera_steg.wav -o data_steg.txt -n 2 -b 10
```
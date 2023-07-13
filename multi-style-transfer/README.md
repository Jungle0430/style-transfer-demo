# Fast Multi Style Transfer
Recommand to download project files (model, vgg, image, etc.) [One drive](https://1drv.ms/f/s!ArFpOdlDcjqQga8fwL0m4VQGmgKSfg) / [Dropbox](https://www.dropbox.com/sh/b3by1ipmr0v821y/AABJ4gadaOk9RRsqsOTC336Xa?dl=0). And Download [COCO](http://mscoco.org/dataset/#download) on your data folder.

### Train

From Scratch
> python main.py -f 1 -gn 0 -p MST -n 5 -b 16 -tsd ../images/content -scw 1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 -sti ../images/styles/style.jpg


Fine-Tuned
> python main.py -f 1 -gn 0 -p MST -n 1 -b 16 -tsd ../images/content -scw 0 1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 -sti ../images/styles/style.jpg \
> python main.py -f 1 -gn 0 -p MST -n 1 -b 16 -tsd ../images/content -scw 0 0 0 0 0 0 0 0 0 0 1 0 0 0 0 0 -sti ../images/styles/style.jpg


### Test
Single style
> python main.py -f 0 -gn 0 -p MST -tsd ../images/content -scw 1 0 0 0 0 0 0 0 0 0 0 0 0 0 0 0 \
> python main.py -f 0 -gn 0 -p MST -tsd ../images/content -scw 0 1 0 0 0 0 0 0 0 0 0 0 0 0 0 0

Multi Style
> python main.py -f 0 -gn 0 -p MST -tsd ../images/content -scw 0.5 0.5 0 0 0 0 0 0 0 0 0 0 0 0 0 0 \
> python main.py -f 0 -gn 0 -p MST -tsd ../images/content -scw 0.4 0.3 0.2 0.1 0 0 0 0 0 0 0 0 0 0 0 0

### Requirements
- TensorFlow 1.0.0
- Python 2.7.12, Pillow 3.4.2, scipy 0.18.1, numpy 1.11.2

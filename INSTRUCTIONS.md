
### darknet
cd darknet
change Makefile for GPU, CUDNN, OPENCV
make
wget https://pjreddie.com/media/files/yolov3.weights
./darknet detect cfg/yolov3.cfg yolov3.weights data/dog.jpg
# how to get video captions as json?



### pix2pix

git clone https://github.com/pytorch/vision
cd vision
python setup.py install
cd ..
rm -rf vision


pip install visdom
pip install dominate


cd pytorch-CycleGAN-and-pix2pix
bash ./datasets/download_pix2pix_dataset.sh facades
python train.py --dataroot ./datasets/facades --name facades_pix2pix --model pix2pix --which_model_netG unet_256 --which_direction BtoA --lambda_A 100 --dataset_mode aligned --no_lsgan --norm batch --pool_size 0



### pix2pix-tensorflow
python tools/download-dataset.py facades
python pix2pix.py  --mode train  --output_dir facades_train  --max_epochs 2 --input_dir facades/train --which_direction BtoA
python pix2pix.py  --mode test --output_dir facades_test --input_dir facades/val --checkpoint facades_train


### char-rnn-tensorflow
cd data
mkdir sherlock
cd sherlock
wget https://sherlock-holm.es/stories/plain-text/cnus.txt
mv cnus.txt input.txt
python train.py --data_dir=./data/sherlock/
python sample.py --save_dir=./save/ -n 200 --prime "hello"


### neural-style

sh models/download_models.sh
th neural_style.lua -style_image examples/inputs/picasso_selfport1907.jpg -content_image examples/inputs/brad_pitt.jpg -output_image profile.png -num_iterations 1000 -image_size 512 


### densecap

luarocks install lua-cjson
luarocks install https://raw.githubusercontent.com/qassemoquab/stnbhwd/master/stnbhwd-scm-1.rockspec
luarocks install https://raw.githubusercontent.com/jcjohnson/torch-rnn/master/torch-rnn-scm-1.rockspec
sh scripts/download_pretrained_model.sh

### neural-enhance

python3 -m pip install --ignore-installed -r requirements.txt

### tensorflow-wavenet

pip install librosa


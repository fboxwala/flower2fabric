Flower2Fabric is a trained CycleGAN model, which tries to take pictures
of flowers, and translate them to the style of floral fabric.

The code in this repository is cloned directly from the [Pytorch implementation
of CycleGAN](https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix).

The only difference is that this repository includes the flower2fabric model,
located in ./checkpoints/flower2fabric. 

Which means this repository has everything one needs to play around with 
flowers and CycleGAN! In theory, CycleGAN works in both directions, which
in this case would mean turning flowers into fabrics and turning fabrics into
flowers. Flower2Fabric does NOT do that. It only turns flowers into fabric, 
and it only kind of does that. You can try the other direction, it will just 
be bad.

## Using the model
To use flower2fabric, you need data to test on! This test data lives in
./datasets/flower2fabric/testA and ./datasets/flower2fabric/testB.

In testA, you want to put all the images of flower you want to fabricize.
testB exists for images of fabrics you want to flowerize, but again, this 
doesn't really work. However, for the model to run you have to put _something_
in there, so I have added an image in that folder.

Using the model to generate floral textiles is pretty easy:

1.  Set up and activate a python3.5 virtualenv, however this works on your 
computer
2. `cd flower2fabric`
3. `pip install -r requirements.txt`
4. `pip install opencv-python` (optional step, needed to use some of the image processing scripts)
5. `python test.py --dataroot ./datasets/flower2fabric --name flower2fabric --model cycle_gan`

And that's all! The output will be dumped into ./results/flower2fabric/test\_latest/images.

If you want to open individual images, your results are the files of the form 
./results/flower2fabric/test\_latest/\*\_fake\_B.png. If you want to see them 
displayed nicely, you can open ./results/flower2fabric/test\_latest/index.html
in your web browser.

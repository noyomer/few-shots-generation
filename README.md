# few-shots-generation
Few shots image generation based 

## Code

### Install dependencies

```
python -m pip install -r requirements.txt
```

This code was tested with python 3.7

###  Train
To train the model on your own batch of images, put the desire training image under Input/Images, and run

```
python main_train.py --input_dir Input/Images/<input_folder>/ --model_name <desired_model_name>
```

This will also use the resulting trained model to generate random samples starting from the coarsest scale (n=0).

To run this code on a cpu machine, specify `--not_cuda` when calling `main_train.py`

###  Random samples
To generate random samples from any starting generation scale, please first train the model for the desire images (as described above), then run 

```
python random_samples.py --input_dir Input/Images/<input_folder>/ --model_name <trained_model_name> --mode random_samples --gen_start_scale <generation start scale number>

```
pay attention: for using the full model, specify the generation start scale to be 0, to start the generation from the second scale, specify it to be 1, and so on. 

###  Quantitative Evaluation
To evaluate the model results with SIFID run

```
python /SIFID/sifid_score.py --path2real <path_to_real_images> --path2fake <path_to_fake_images>
```

# SinGAN
[Project](http://webee.technion.ac.il/people/tomermic/SinGAN/SinGAN.htm) | [Arxiv](https://arxiv.org/pdf/1905.01164.pdf) | [CVF](http://openaccess.thecvf.com/content_ICCV_2019/papers/Shaham_SinGAN_Learning_a_Generative_Model_From_a_Single_Natural_Image_ICCV_2019_paper.pdf) 
### Official pytorch implementation of the paper: "SinGAN: Learning a Generative Model from a Single Natural Image"
####  ICCV 2019
SinGAN Repository: https://github.com/tamarott/SinGAN

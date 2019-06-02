# Resume_Fillv1
Based on [fillv1](https://github.com/JiahuiYu/generative_inpainting) from Jiahui Yu, the change focus on the inpaint.yml.

## Training
When you are training from zero, the MODEL_STORE flag should be nothing.

## Resume Training
The MODEL_STORE flag should be the last model_logs location. Please read train.py.
```python
ng.callbacks.ModelRestorer(trainer.context['saver'], dump_prefix='model_logs/'+config.MODEL_RESTORE+'/snap', optimistic=True),
```

## Tips during training
1. The file tree can be:
   ```
   project
   └───training_data
   │   │───training
   │   │    └───celeba
   │   │    	│───image0.jpg
   │   │   	│───image1.jpg
   │   │   	│───...
   │   └───validation
   │   │	└───val_celeba
   │   │    	│───image162771.jpg
   │   │   	│───image162772.jpg
   │   │   	│───...
   └───data_flist
   │   │───training_shuffled.flist
   │   └───validation_shuffled.flist
   └───model_logs
   └───neuralgym_logs
   └───train.py
   └───test.py
   └───impaint.yml
   └───...  

   ```
2. You can change the IMAGE_SHAPES in inpaint.yml to speed up.
   ``` python 
   IMG_SHAPES: [256, 256, 3]
   ```
   The size of mask will be changed automatically. Please read inpaint.ops.py.
 
 

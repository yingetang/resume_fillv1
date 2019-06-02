# resume_fillv1
based on fillv1 from Jiahui Yu, the change focus on the inpaint.yml.

## training
when you are training from zero, the MODEL_STORE flag should be nothing.

## rusume training
the MODEL_STORE flag should be the last model_logs location. Please read train.py.
```python
ng.callbacks.ModelRestorer(trainer.context['saver'], dump_prefix='model_logs/'+config.MODEL_RESTORE+'/snap', optimistic=True),
```

 

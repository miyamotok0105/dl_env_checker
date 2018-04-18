# dl_env_checker

.                                                  | Deepo
:------------------------------------------------: | :----------------:
 [ubuntu](https://www.ubuntu.com)                  | 16.04
 [cuda](https://developer.nvidia.com/cuda-zone)    | 9.0
 [cudnn](https://developer.nvidia.com/cudnn)       | v7
 [theano](http://deeplearning.net/software/theano) | :x:
 [tensorflow](http://www.tensorflow.org)           | :heavy_check_mark:
 [sonnet](https://github.com/deepmind/sonnet)      | :x:
 [pytorch](http://pytorch.org)                     | :heavy_check_mark:
 [keras](https://keras.io)                         | :heavy_check_mark:
 [lasagne](http://lasagne.readthedocs.io)          | :x:
 [mxnet](http://mxnet.incubator.apache.org)        | :heavy_check_mark:
 [cntk](http://cntk.ai)                            | :heavy_check_mark:
 [chainer](https://chainer.org)                    | :heavy_check_mark:
 [caffe](http://caffe.berkeleyvision.org)          | :x:
 [caffe2](https://caffe2.ai)                       | :x:
 [torch](http://torch.ch/)                         | :x:
 

deepo    
https://github.com/ufoym/deepo    


## ja

deep learning検証環境の動作チェック用。    
deepoでdockerで入れると多くの環境を一括で構築できる。    


### コマンド    

mnistが動くことを確認。    

```
cd deepo_001
python chainer_3.5.0.py -g 0
python cntk_2.4.py
python keras_2.1.5.py
python mxnet-cu90_1.1.0.py
python pytorch_0.3.1.py
python tensorflow-gpu_1.5.0.py
```


### gpu使用状況の確認

```
watch -n1 "nvidia-smi"
```

gpuを使ってない場合はプロセス（Processes）が空の状態。    


```
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 390.25                 Driver Version: 390.25                    |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  Tesla K80           Off  | 00000000:00:04.0 Off |                    0 |
| N/A   30C    P0    57W / 149W |      0MiB / 11441MiB |    100%      Default |
+-------------------------------+----------------------+----------------------+
                                                                               
+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID   Type   Process name                             Usage      |
|=============================================================================|
|  No running processes found                                                 |
+-----------------------------------------------------------------------------+
```

gpuを使ってる場合はメモリが変化する。    
下の例は10952MiB使っている。    
またプロセス（Processes）に実行中のプロセスが入る。    


```
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 390.25                 Driver Version: 390.25                    |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  Tesla K80           Off  | 00000000:00:04.0 Off |                    0 |
| N/A   34C    P0    63W / 149W |  10952MiB / 11441MiB |     56%      Default |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID   Type   Process name                             Usage      |
|=============================================================================|
|    0      1134      C   python                                     10939MiB |
+-----------------------------------------------------------------------------+
```


## English

Operation check of deep learning research environment.    
If you put it in docker with deepo, you can build many environments in bulk.   


### Command    

Confirm that mnist works.    


```
cd deepo_001
python chainer_3.5.0.py -g 0
python cntk_2.4.py
python keras_2.1.5.py
python mxnet-cu90_1.1.0.py
python pytorch_0.3.1.py
python tensorflow-gpu_1.5.0.py
```

### Confirm gpu usage


```
watch -n1 "nvidia-smi"
```


If gpu is not used, the process (Processes) is empty.


```
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 390.25                 Driver Version: 390.25                    |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  Tesla K80           Off  | 00000000:00:04.0 Off |                    0 |
| N/A   30C    P0    57W / 149W |      0MiB / 11441MiB |    100%      Default |
+-------------------------------+----------------------+----------------------+
                                                                               
+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID   Type   Process name                             Usage      |
|=============================================================================|
|  No running processes found                                                 |
+-----------------------------------------------------------------------------+
```

Memory area changed when using gpu.    
The example below uses 10952MiB.    
Processes are also running processes.    


```
+-----------------------------------------------------------------------------+
| NVIDIA-SMI 390.25                 Driver Version: 390.25                    |
|-------------------------------+----------------------+----------------------+
| GPU  Name        Persistence-M| Bus-Id        Disp.A | Volatile Uncorr. ECC |
| Fan  Temp  Perf  Pwr:Usage/Cap|         Memory-Usage | GPU-Util  Compute M. |
|===============================+======================+======================|
|   0  Tesla K80           Off  | 00000000:00:04.0 Off |                    0 |
| N/A   34C    P0    63W / 149W |  10952MiB / 11441MiB |     56%      Default |
+-------------------------------+----------------------+----------------------+

+-----------------------------------------------------------------------------+
| Processes:                                                       GPU Memory |
|  GPU       PID   Type   Process name                             Usage      |
|=============================================================================|
|    0      1134      C   python                                     10939MiB |
+-----------------------------------------------------------------------------+
```



# Licensing

Deepo is MIT licensed.


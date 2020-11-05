[tensorflow]: https://www.tensorflow.org/install

# ToolsDeepLearning

```

set of technologies in which its use, implementation, and limits are explored

```

## Getting started:

```

Each notebook focuses on a different technology, there is no dependency between files

```


### Requirements


python interpreter

And the library:

numpy, sklearn, pandas, seaborn, scipy, matplotlib, tensorflow, tensorboard

the simple way for install

```
!pip install 'select library' -> Jupyter
 pip install 'select library' -> console into python interpreter
```

### Build Requirements

#### For uses Tensorflow:

Normally install it the first time it is simple, everything works is more complicated, 
this is tested for CUDA v10.2, once the tutorial in [tensorflow] is completed,
and you have add the respectives PATH to enviroment
there is usually a quite annoying error, where the cupti64 file has the wrong name, 
simply changing it to the correct name should work


This can happen with other files. Before modifying anything, make sure that 
you have followed all the steps in the tutorial, and that the file to be modified
has the same size with a slightly different name, for example cudart64_102.dll 
is sometimes called cudart64. dll

install tensorflow last version (works with  v2.3.0)
import tensorflow as tf

and that's it



### For uses Tensorboard:


install tensorboard last version (works with 2.3.0)
import tensorboard       as tb
%load_ext tensorboard
logdir="logs/MNIST-Convolutional-DataAugmentation"

tf.profiler.experimental.start(logdir=logdir)

*** Do the work ***

tf.profiler.experimental.stop()


Now we have the data let's explore it



%tensorboard --logdir="logs" --port=6006 >>> default 127.0.0.0:6006 or localhost:6006 if you have DNS

This service does not have a way to restart, 
the normal thing to do is to kill it, and restart it with a different port,
because when you kill it that address remains used during the loan time




## License

```

MIT License

```

# ToolsDeepLearning

A collection of Jupyter notebooks exploring core deep learning techniques, architectures, and best practices using [TensorFlow](https://www.tensorflow.org/) and [Keras](https://keras.io/). Each notebook is self-contained and focuses on a distinct topic — no dependencies between files.

---

## Notebooks

### 🔢 SimpleLinearRegressionInTensorflow
Introduction to TensorFlow fundamentals: tensor operations, [gradient tape](https://en.wikipedia.org/wiki/Automatic_differentiation), and building a [linear regression](https://en.wikipedia.org/wiki/Linear_regression) model from scratch on the Boston Housing dataset. Includes TensorBoard scalar logging.

### 🧠 MultilayerPerceptronClassificationImage
Image classification on MNIST using a [Multilayer Perceptron (MLP)](https://en.wikipedia.org/wiki/Multilayer_perceptron) built with fully connected Dense layers. Covers training, validation, and visualizing misclassified examples.

### 📊 DataAugmentationMNIST_BCW
Demonstrates the impact of [data augmentation](https://en.wikipedia.org/wiki/Data_augmentation) (translation, rotation, noise) on model robustness with MNIST. Also includes a binary classification baseline on the [Breast Cancer Wisconsin dataset](https://en.wikipedia.org/wiki/Breast_cancer_Wisconsin_(diagnostic)_data_set). Includes a discussion on why augmentation may not always be appropriate depending on the domain.

### 🖼️ ConvolutionalNeuralNetworksMINIST-Cifar100
[Convolutional Neural Networks (CNNs)](https://en.wikipedia.org/wiki/Convolutional_neural_network) applied to MNIST with data augmentation, and then scaled up to [CIFAR-100](https://en.wikipedia.org/wiki/CIFAR-10) with a deeper architecture, [batch normalization](https://en.wikipedia.org/wiki/Batch_normalization), and Keras `ImageDataGenerator`. TensorBoard profiling included.

### 🔁 AutoencoderDenseConvolutional
Two [autoencoder](https://en.wikipedia.org/wiki/Autoencoder) implementations on MNIST:
- **Dense autoencoder** — compresses images into a 2D latent space for visualization.
- **Convolutional autoencoder** — uses Conv2D/Conv2DTranspose layers, demonstrates denoising and [latent space](https://en.wikipedia.org/wiki/Latent_space) interpolation between digits.

### 📝 NaturalLanguageProcessing
Character/word-level sequence modeling using [Recurrent Neural Networks](https://en.wikipedia.org/wiki/Recurrent_neural_network) ([LSTM](https://en.wikipedia.org/wiki/Long_short-term_memory)) and [word embeddings](https://en.wikipedia.org/wiki/Word_embedding). Trained on a Spanish poem to generate text token by token.

### 😊 SentimentAnalyzer
[Sentiment analysis](https://en.wikipedia.org/wiki/Sentiment_analysis) on the IMDB movie review dataset using an Embedding + LSTM model. Includes exploration of the learned embedding space via [PCA](https://en.wikipedia.org/wiki/Principal_component_analysis) and word frequency analysis.

### ⚠️ Overfitting
Systematic comparison of [regularization](https://en.wikipedia.org/wiki/Regularization_(mathematics)) strategies to combat [overfitting](https://en.wikipedia.org/wiki/Overfitting) on IMDB text data:
- [Dropout](https://en.wikipedia.org/wiki/Dilution_(neural_networks))
- [Batch Normalization](https://en.wikipedia.org/wiki/Batch_normalization)
- [L1 and L2 weight decay](https://en.wikipedia.org/wiki/Regularization_(mathematics)#L1_and_L2_regularization)
- [Early stopping](https://en.wikipedia.org/wiki/Early_stopping)

### ⏱️ TemporalSeriesAnalyzer
[Time series](https://en.wikipedia.org/wiki/Time_series) forecasting on the UCI Household Power Consumption dataset using a [Bidirectional LSTM](https://en.wikipedia.org/wiki/Bidirectional_recurrent_neural_networks). Includes correlation heatmaps, resampling analysis, and multi-step input windowing.

### 🔀 Transfer Learning
[Transfer learning](https://en.wikipedia.org/wiki/Transfer_learning) with [VGG16](https://en.wikipedia.org/wiki/VGGNet) pretrained on ImageNet, fine-tuned for cats vs. dogs classification. Compares a custom CNN baseline against the pretrained feature extractor with a [frozen backbone](https://en.wikipedia.org/wiki/Fine-tuning_(machine_learning)) and subsequent fine-tuning.

---

## Requirements

```
numpy
pandas
scipy
sklearn
matplotlib
seaborn
tensorflow >= 2.3.0
tensorboard >= 2.3.0
```

Install any library with:
```bash
pip install <library>         # terminal
!pip install <library>        # Jupyter cell
```

### GPU / CUDA Setup

Tested with **CUDA v10.2**. After following the [TensorFlow GPU installation guide](https://www.tensorflow.org/install/gpu), if you encounter a missing or misnamed CUDA file (e.g. `cupti64` or `cudart64.dll`), check that the file exists with a slightly different name and rename it accordingly — do not modify anything before verifying the sizes match.

### TensorBoard

```python
import tensorboard as tb
%load_ext tensorboard

# Start profiling
tf.profiler.experimental.start(logdir="logs/my-run")
# ... training ...
tf.profiler.experimental.stop()

# Launch in notebook
%tensorboard --logdir="logs" --port=6006
```

Default address: `http://localhost:6006`. If a port remains in use after killing TensorBoard, restart with a different port number.

---

## License

[MIT License](LICENSE) © 2020 qwerteleven
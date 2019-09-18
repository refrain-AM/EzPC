This folder contains code for compiling the [Chest X-Ray demo](https://blogs.technet.microsoft.com/machinelearning/2018/03/07/using-microsoft-ai-to-build-a-lung-disease-prediction-model-using-chest-x-ray-images/) based deep neural network using Athos. [Here](https://github.com/Azure/AzureChestXRay) is the original github repo for the blog, which contains its code.

## Setup
- Run the script `SetupPretrainedTFModel.sh` which sets up the pretrained model in a form which can be subsquently be used by Athos. For this, it first downloads the pretrained Keras model from [this link](https://chestxray.blob.core.windows.net/chestxraytutorial/tutorial_xray/chexray_14_weights_712split_epoch_054_val_loss_191.2588.hdf5) (found from the original github repo). Thereafter, it sets up the [Keras to TensorFlow converter](https://github.com/amir-abdi/keras_to_tensorflow) and converts the Keras based model to the TensorFlow based model and places the same in the folder `./PreTrainedModel/TFModel/`.
- Once the pretrained model is setup, run the following command to dump the TensorFlow metadata, for further use by Athos.
`python3 ChestXRay_tf_main.py --runPrediction True --scalingFac 12 --saveImgAndWtData True`
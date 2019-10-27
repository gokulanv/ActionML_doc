# Functional API

## CNNModel.py

### Data Loader
```
class CNN_Loader_with_SIFT(Sequence: 'Keras.utils.Sequence')
```
> Class data generator for loading batch of images along with SIFT features.

```
class CNN_Loader(Sequence: 'Keras.utils.Sequence')
```
> Class data generator for loading batch of images without SIFT features.

```
data_train_test(data: 'pandas.DataFrame', split: 'float')
```
> This function splits the given dataset into train and test data based on the split ratio given.

### Building Models
```
build_model_with_sift()
```
> Creates a parallelized architecture for using raw images with Xception(pre-trained weights) and SIFT features with a dense block. The architecture later combines the two branches and gives the final prediction. The model is compiled using Adam Optimizer and binary cross entropy loss.
```
build_model()
```
> Creates a simple architecture for using raw images with Xception(pre-trained weights) along with a custom classifier layer. The model is compiled using Adam Optimizer and binary cross entropy loss.

### Model functions
```
training_model(train_data_generator: 'CNN_Loader', eval_data_generator: 'CNN_Loader', model: 'Keras.models.Model')
```
> This function takes the built model and trains using the "train_data_generator". Validation accuracy is monitored for every epoch.

```
predicting_model(eval_data_generator: 'CNN_Loader', model: 'Keras.models.Model')
```
> This function uses the given model to predict the probabilities of classes for the evaluation data generator.

```
scores(y_pred: 'Array', y_true: 'Array')
```
> This function calculates the accuracy, precision and recall score. -> Action.ml Output

## InferenceModel.py
> Uses the same class loader as above.

```
load_model(name: str)
```
> Loads the model specified by name.
```
write_images(image_paths: list(str), predictions: Array, dest_path: str, task_name: str)
```
> Writes the predicted labels on the images and saves them in the dest path
```
create_video(path_to_dir: str, image_paths: list(str))
```
> Stitches the images in path_to_dir into a video
```
inference_model(task_name: str, SIFT: Boolean)
```
> Master inference function that loads the model, creates the data_generator object, gets the predictions and scores them. It also creates the video for labelled images.

## ActivationMap.py
```
cam(img_path: str)
```
> This function loads an image from the given path and gets the heatmap for the activation from the last block in the model.
```
load_model(name: str)
```
> The function loads the given model.
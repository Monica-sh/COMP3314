# COMP3314_a2
COMP3314 Assignment 2 - CNN

> **Using PyTorch to construct CNN for a 10-category classification problem which classifies digit images into 0-9.**

### Author: Guo Shunhua 3035447635 

## Functions

**1. model.py defines net structure.**

Only the CNN structure is defined, and I am using 

> ***Conv - Conv - ReLU - MaxPool***
>
> ***Conv - Conv - ReLU - MaxPool***
>    
> ***FC - ReLU - Dropout - FC - ReLU - FC***

as my CNN structure.

**2. main.py defines the parameters and the train-test procedure.**

```
train(model, criterion, optimizer, scheduler, num_epochs=25, save_name=None, if_eval=False)   
```
`train(...)` constructs the major training process.

If `save_name` is not `None`, then it will store the model trained and the loss, time spent, and `PARAM` to `results` directory under `save_name` name.

If `if_eval` is `True`, then the training process will not evaluate the model on test dataset on each epoch, this will require around 28s for each epoch. But it should be really helpful to check if the model is overfitted or not. This will call `test(...)` at the end of each epoch.

```
test(model, if_print_total=True, if_print_class=True)
```
`test(...)` will return accuracy on test dataset, and accuracy on each class on test dataset.

 `if_print_total` and `if_print_class` decide if you want to see the test accuracy result print to terminal.
 
    
**3. utils.py contains help functions, like for loading the dataset, and storing the loss and accuracy result.**
```
data_loading(data_dir='data', PARAM=None)
save_result_n_model(save_name, data, model)
restore_model(save_name)
```
Those utility functions are defined here, and they are callable from main.py.

**4. result visualisation (Jupiter notebook) provide a visualisation for loss and accuracy result on the trained model or training process.**

> Introduction
> Read Result
> Visualization of Loss and Accuracy for single case
> With and without ReLU activation layer comparison
> Parameter Analysis

It has the above sections.

## Restoring procedure

To restore my best model trained, run `model = restore_model('best')` in main.py, 
and it will give the best model I have trained on the data set.

## Training procedure

To train the model in this data set and retrive the performance on test dataset, 
simply run main.py (the procedure is listed in `main()` function).

And you can change the parameters in `PARAM`.


### Dataset AND training result
Data set used is provided in the folder named 'data'.

The training set contains 3,000 samples for each class and the testing set contains 500 samples for each class. Each input image has three channels and each channel contains 32*32 pixels.


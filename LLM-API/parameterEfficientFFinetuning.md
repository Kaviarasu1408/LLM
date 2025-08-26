## Parameter Efficient Finetuning

## 1. LORA

- In LORA, we will freeze the layers..so while finetuning..the pretrained layers weights will not get updated..
- Instead of updating all layers, you choose specific layers (usually the attention layers, like q_proj, v_proj) as target modules.
- Only these target modules will get learnable adapters added.
- creater a new adaptor matrices with lower dimensions with fewer parameters.
- Apply these adaptor to the target modules,It will adapt them.These adapter we are training it's for specific task..

## 2. Quantization - the Q in Lora(Quantized low rank adaption)

- if we use quantization it will reduce the memory of the model to fit in.
- we can reduce the precision from 32 bit to 4 or 8 bits..
- using lora we can freeze all the layers
- we can add adapter, only these layers will be trained..

## 3. How does it work

- Take a pretrained model (e.g., LLaMA-7B).
-  it to 4-bit precision → now it fits on smaller GPUs.
- Add LoRA adapters → small trainable parameters in each layer.During training:
- Quantized model weights stay frozen.
- Only LoRA adapters update.

## 3. Hyperparameter

- r(rank) : when u finetune instead of updating huge weight matriz say(4096 X 4096), LORA adds adapter.The size of the adapter is controlled by rank r.Higher or Lower which is more trainable parameter or lighter and cheaper parameter
- alpha : How strong the adapter is in the basemodel, if alpha is larger..higher influence or lower influence
- target modules : we need to choose in which layer we need to add adapters..that is called target modules..choose querky,key and value .


## 4. Using open source base Model for predicting the price

- select the base model which llama..
- LogIn to the hugging face, download the dataset from hugging face and take the training and testing data..
- Llama model is taking a three digit number as a 1 token.
- prepare the base model for evaluation..
- first intialize the quantization which is 4 bit
- use AutoToKenizer.from_pretrained() to tokenize the text.
- we can use AutoModelForCausalLM.from_pretrained() in the parameter pass the base_model and quanization .'
- we can write the function, which encode the prompt and pass the input to get the output
- but still it's not predicting the right output
- we can create a loader class to check all the testing data.

## 5.Model performing 

Traditional ML Model - Avg $139
Random forest - Avg $97
GTP-4O - Avg $76(Prompting)
(Open source)Llama 3.1 Base 8B - Avg $396 


### 6.Five Important Hyper-parameters for Qlora

## 1. Target Modules

- we have transformer architecture, fro train those all the layers it will take time, we can pick few layers..we can call this a target modules..we freeze everything..we will add adapters
- we have these lower dimesnional matrix, we will train these matrix..we apply these to the original target modules..

## 2. r(Rank)

- How many dimensions we have in the lower dimensioanl adapter matrxix
- size of the matrix..

## 3. Alpha

- scaling factor
- It is used to multiply up the importance of this adapter in the target module
- rule of thumb alpha is double as R.

## 4. Quantization

- reduce the memory of the model to fit in..
- quantize from 32 bit to 8 or 4 bit.
- reduce the precision of the modell..

## 5. dropout

- dropout 
- help to prevent the model from overfitting..
- remove random subset of neurons in the transformer architecture..
- expect all the neurons to participate..
- everytime remove some percentage..

### 7. Five Important Hyper-parameters for Trainingg

## 1. Epochs

- How many times you are going through the entire datasets as part of the training process..
- You can reduce the loss..if you going through the epoch 2nd times.
- Every epoch we are making a very small steps in the direction of making the model a little bit better..
- shifting the weight in the laura matrice..based on the loss..so the next time it will do better,,

## 2. Batch Size

- we don't take one data point and put it through the forward pass of the model to predict the next token..calaculate the loss and then go backwards..figure out of the gradients of how much does that the loss.
And then optimize the model by doing little step in the right direction..
- we can do this with bunch of data together..
- we can often pick a four or 8 or 16..you can do it togehther for all 16.
- each epochs we can send 16 datapoints in the epoch to predict the output and calculate the loss..
- after each epoch we can test the model performance at the end..
- the model will do better and better after each epochs..but when you reach the certain point where the model starts to overfit..where it is starts to get used to seeing the training data..when you test it model performance get worse..because it;s not expecting points outside its training dataset..
- we start to see like better, better,worse..worse..
- we can pick the epoch which gave you the best model, the best outcome..and that's the one that you consider the resuls of ypur training..
- run larger number of epochs and then pick  the best epoch for the testing data..

## 3. Learning Rate

- Take your model, take the traing datapoint..do a forward pass..
- predict the next token
- we can take the probability and precition and calculate the loss..
- take the loss, do backward propogation..how much would i have to tweak each weights up or down in order to do a little bit better next timee..
- you have to take the step in the direction to do better in the next time, you have to shift your weight, a step in the direction to do better next time.
- the amount you shift your weight in the good direction so that it will do better next time..It's called learning rate..

## 4. Gradient Accumualtion

- Techique to improve speed of going through the training..
- we are going to do is we are going to we normally do a forward pass..we get the loss..we do backward propagation to update the weight..and step in the right direction..
- Gradient accumulation sayss..we do forward pass get the gradients..do second forward pass get the gradients..do this pass few more times..
- And then step backward pass..

## 5. Optimizer

- once you got the gradient and learning rate..
- we need to update you neural network to shift little bit in a good direction..
- so that next time it predicts the right next tokemn

## Notes : 

- Epoch will go through the entire dataset once, if we do multiple epochs the model will do better..That's why companies will train with larger epoch.
- we have training data and validation data.The model will performs good with training data..since we are doing multiple epoch the model will be so much better..models will be too domaint..it also memorize training data..so it perform well in the training data and the validation loss will become higher..it's called overfitting..
- So for this we use dropout..dropout will turn-off the neurons in every epoch..so that the learning will be shared across the neurons..so that all the neurons will participate in the training..so that it will not rely on one-neuron
- we do forward pass..for each epoch we send the data in batches..so that we do forward pass..predicte the next word..calculate the loss..for the batch..do the backward pass
- gradient will tell in which direction we need to go..
- learning rate how much step we need to take in that direction..
- optimizer optimize the weights in the new directions..
- we can take the best epoch with training and validation loss is lower and predicts the next word..
## Model Initialization with pretrained weights

- In the code we define the model of 124 M.
- we set base_config like voc_size, context length..
- update the base_config with config model..
- And the condition - we are going to remove all the token which are higher length than the context token..

    ![alt text](Images/model1.png)

- download the gpt2 parameters..and return settings and params..
- settings contains configuration details and params contains trainable weights..
- we can define the model and using load_weight_into_gpt we can load the weights into gpt model..

    ![alt text](Images/model2.png)

- without any classification or finetuning the model lacks the perform for checking spam or not spam

    ![alt text](Images/model3.png)

- modify the classification head
- In the final output layer of transformation, instead of vocab_size in the column we need to replace with spam or not spam..2 columns..
- add a classification head only 2

    ![alt text](Images/model4.png)

    ![alt text](Images/model6.png)

- freeze all the layers...we can use req_grad=false to freeze all the layer..we are not going to update..freeze it..all the parameter...

    ![alt text](Images/model5.png)


- Not necessay to fine tune all the layers - only fine tune the last layer...make trainable last layer..make req_grad = true for all the layers..

    ![alt text](Images/model7.png)

- 12 transformer block - fine tune the last year..no need to fine tune all the blockss..reduce computation..

- final output..final norm layer..final transformer..we can freeze the others..

- we can take the last token it has all the values..

    ![alt text](Images/model8.png)
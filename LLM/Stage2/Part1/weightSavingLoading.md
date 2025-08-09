## Weight Saving & Loading

- torch.save(model.state_dict(),"model.pth")
- using torch.save(), we can save the parameter..Instrad of running the GPT Model again and again..we can save it..
- state_dict() its a dictionary maps each layer to its parameter.
- model.pth - we can save all the parameters in the file name..its file name to save it..

- model.load_state_dict(torch.load("model.pth"))
- let say u saved the parameter and you send it to someone else..
- when they load the file using torch.load() - all the parameters are loaded 

## Optmizer

- Optimizer maintans the histroy of gradient and square gradient.
- if i save the model parameter..the optimizer will estenially loses the gradient values and the square gradinet value...which has calculated untill the training process
- saving optimizer is also recommended...optimizer can be saved using optimizer_state_dict()
- it stores the hyperparameter and it also stores the hystroical data used by the optimizer such as past gradients values and square of the gradient values...
- Adamw uses hystorical daata to adjust the learning weigh parameter dynamically such as gradient or history of the gradient..
- using torch.save we can save both the model and optimizer also..in same file...itself..

- we can test this using torch.load()
- we can define the model and load the model
- we define the optimizer and load the optimizer..
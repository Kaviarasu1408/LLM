## Finding the dataset

- your own proprietary data(Company data)
- Kaggle
- HuggingFace
- Synthetic data(Shared drive)
- scale.com

## Refinement data(Improve the data quality)

- Investigate and understand the data
- Parse 
- Visualize the data
- Assess the data quality, removed unwanted if any
- curate(craft the datasets),
- save.

## Model predicts the price of the product based on the description

- we take the Amazon product review dataset from the hugging face and the dataset will be available on the particular folder.
- Imports and Initialize the api
- Load the dataset and choose only appliance categories.
- Investigate and understand the dataset and check how many with the , we only data with price so that the model will predict.
- we are going to check the length of the descriptions, features and length to identify how much token we need to send to the model
- plot the data to visualize.
- we need to select items that cost bt 1 and 999 USD, we will be create item instance..which trucate the text that fits within 180 tokens using the right tokenizer.
- This class Item is designed to take product data + its price and then convert it into a cleaned, tokenized prompt for training/testing a language model (like LLaMA-3.1).
- we will create a prompt for training data.this is called hyper-parameter.we need to have large number of token so that it can predict the price.
- now we can curate, we have items.py it takes llamma model and we need to pass 2 inputs the datapoints and price..intialize the title,prices and categories and prompt
- it removes the certain fields and cleans out the weird character and parse it with the prompt data
- Create Item object in jupyter lab and check.
- Creates a training prompt: question + product info + correct answer.
- Provides a test prompt: same but without the answer.

## Performance Evaluation

- we can do it 2 ways, one is model centric and business centric
- **Model Centric :** how well the model is performing like we calculate the training loss/validation loss and also RMSLE.
- **Business Centric :** How well the model is predicted like if it is predicted the price..what is the actual price and what is the predicted price and we can caluculate the difference..
## Five Step Strategiess for business usecases

- Understand the data (Quality/quantity), check the requirement and gather information abt the data.
- Prepare the datasets check for the existing solution and currate the data which means pre-processing and cleanup the data.split the dataset into training/testing data.
- Select the right model(LLM) and pass the currated datasets to the LLM
- customize the model using prompting(frontier models),RAG(Accuracy without cost of finetuning) or Finetune(for specific task high vol of data).
- Productionize defining the api for frontier or opensource model, host and deploy, monitor, measure the business metrics and measure the performance.

- we have loaders.py,basically we load the datasets and chunk the data into 1000 datapoinst..so in each chunk we have 1000
- we can create the dictionary which is slot..key is the price which is from 1 dollar to 999 dollar.val is the list of product all the items for that particular prices..
- for 2 dollar key which is in slot2 have products which cost is 2 dollars..
- go through each of the slots sample it from all these slots as a subsets.so it will have a balanced datasets.
- if anything worth more than 240 dollars, take the whole slot add in the sample and if it is less than take only few items like only 1200 datapoints add in the sample..
- shuffle the datasets and get the training and testing

## Loading pre-trained open AI weights

- load pre-trained weights from open AI into out LLM Model
- In our LLM, we trained GPT with a small datasets using a book right.
- this give us result but we didn't get the proper meaning of it..
- Open AI shared their weights publicly..we are going to loading this weight into out GPT Model..for next text predictions..
- open ai saved their weights via tensorflow..and we use another libaray called tqdm for download tracking...
- we have this download_and_load_gpt2() to download all the files from the openapi modules..
- settings contains the configurations..
- params contains all the weight tesnors..
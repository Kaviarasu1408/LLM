## RAG (Retrieve Augmented Generation)

- In RAG, In the chat user first ask the question and in the code before we sending it to LLM we can check in the knowledge base whether we can have any relevant information.
- After that only we send it to the LLM and LLM responds..

    ![alt text](Images/rag1.png)

## Building the RAG

- If you are working on usecase which is Insurance tech company, we need to have knowlwdge base as a folder inisde it we can have different folders like company(carrers,about,overview), contracts(companies contracts), Employees(HR Details) and products(Product details).all this are company data. 
- we are going to use python function called glob.glob() - this will look for the files in the particular folder and initalize it to the variables..
- we are going to iterate the files and open the file one by one and put it in the dictionary..
- construct the dictionary look for the message in the dictionary..
- construct the system, user, assistant to expect as gpt model and work
## Multi Head Attention Mechanism

- Running causal self attentions multiple times..
- Dividing the attention mechanism into multiple heads
- Each heads operating independently
- create mltiple instance of self-attention mechanism each withs its own weights and then combaining their output..
- This makes LLM Performs much better.

    ![alt text](../Images/multiHeadAttention.png)

- We have a input vector embedding for a words.
- Now we need to have trainable weight matrices for each queries(Wq1,Wq2), keys(Wk1, Wk2) and values(Wv1,Wv2).
- Now calculate the query,key and value by multiplying wq1*input,wq2*input, and so on..
- Now we have query1,query2,key1,key2,value1,value2 and so on.
- calculate the attention score separately for each queries,keys by multiplying it.
- calculate the attention weight.
- And now finally for each attention weights, multiply it with respective values to the context vector..
- Now we have 2 context vector and concat the 2 context vector.

    ![alt text](../Images/contextVectorMultiHead.png)


## Coding Multi head Attention

- If the number of head is 5, we can create 5 instance of causual attention class and we concat it together.

    ![alt text](../Images/codingMultiHeadAttention.png)
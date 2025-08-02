## Data Preparation and Sampling

## How do you prepare a input text for training LLM ?

- Break the sentence into a individual words for a token or tokenization text.
- Assign tokens Ids into each token.Each token Ids are associated with the token.
- Encode the token Id with vector embedding.
- After that it will fed as an input data to the gpt.

    ![alt text](../Images/tokenEmbedding.png)


## 1. Load the file in Jupyter Notebook.

- Upload the file in jupyter notebook.
- And then with_open to check how many characters and the words.

    ![alt text](../Images/loadFile.png)

## 2. Split the Sentence to tokenization

- for splitting the sentence we can regular expression libaray.
- split() function to split whitespaces(\s), comma(,) and full stop(.) and now you can print the result.

    ![alt text](../Images/splitSentence.png)

## 3. remove the whitespaces.

- Removing the whitespace to reduce the memory and computional.
- But python is case sensitive, for training LLM we need to have white senisitive it has some meaning.
- White spaces are important, because indedention matters for sensitive the data.

![alt text](../Images/whitespace.png)

## 4. Split the sentence with special characters.

- We have some more special character, we need to split all those special character.

    ![alt text](../Images/removeSpecial.png)

## 5. Split the actual Text

- Split the actual text with spaces and special characters as token.
- Remove the spaces using strip() to remove the white spaces.
- print the length.

    ![alt text](../Images/ActualSplitData.png)

## 6. Assigning a token Id to token.

- Once we created a token, we need to build a vocubulary.
- Vocubulary is a list of token in an alphebectical order.
- Each unique token will be mapped to the unique integer called token Id.
- We have billions of data, Vocubulary will be hugee.


## 7. Now for our data

- Convert our data as set sort the set.
- Once you sorted you only get unique text.
- Assign the unique text a unique number and print it.
- Dictionary contains indvidual token associated with the token Id.

  ![alt text](../Images/sort.png)
  ![alt text](../Images/unique.png)

## 8. LLM Output

- Now whatever we done its an encoder.
- But once we giving the output, we need decoder to convert a token id to text.

## 9. Implement a Tokenizer class for Encoder and Decoder.

- Token Encoder gets the input as text, convert the text into token and token Ids.
- Token Decoder gets the token Id as an input, convert the token Id to token and the actual text.

    ![alt text](../Images/tokenEncode.png)
    ![alt text](../Images/tokenDecoder.png) 

## 10. Create a class for tokenizer encoder and decoder

- If you didn't pass the input that are not present, it will throw an error.Because it's not in the training datasets.That's why we need to train larger datasets.
- Create an class and checks for encoder and decoder, we can have 2 function.one function is for encoder and and another function is decoder.
- if we call encoder with input text, it will give us token ids.
- if we call decoder with token ids, it will return the text based on the token Ids.

![alt text](../Images/classEncoderDecoder.png)
![alt text](../Images/encoderDecoderOut.png)

## 11. Special Context Token

- We can train the model to handle the unknown words. If the word is not there in the trained data it thrown an error.For that we need to use special context token.
- we have 2 things here |ukn| which is unknown and |endotex| which is end of text.
- we have data quickly, if quickly is not there in the pretrained data..It will take |ukn|.
- End of text, let say we are training multiple resource like book, reseach paper and after each source trained we can add |endoftext|.so that model can know where is the ends.

## 12. Special token to work

- Add |ukn|, |endoftext| is the vocab and add integer like token Id.

![alt text](../Images/specialToken1.png)
![alt text](../Images/specialToken2.png)
![alt text](../Images/specialToken3.png)

## 13. Additional context tokens

- BOS(Beginning of sequence)
- EOS(End of sequence)
- Padding

## 14. Byte Pair Encoding

- BPE to handle the unknown words in the LLM Models.
- Here the words itself divided into sub words that will be consider as a token.
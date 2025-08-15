## Loading pre-trained LLM

- there are lot of pre-trained weights..
- more than 100 million parameters..
- open-ai trained and optimized the weights..and released those weights..
- 4 diffferent models..134M, 155M, 345..
- why are we downloading this weights..
- lot of informations are captured correctly..already pre-trained..
- for example while we doing token embedding..we want to project the words or tokens into higher dimensional vector...we want to projct them so that the semantic meaning is capturedd..
- to train a neural network again from the scratch will take lot of computational cost...
- instead we can directly use pre-trained gpt2 weights..
- instead of random initializing and training from the scratch..the model starts from much knowledgeable state..so the computational time it takes to train will be reduced
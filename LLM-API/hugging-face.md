## Hugging Face

Offers you three things,

- Models : All the models available for you
- Datasets,
- Spaces.


HuggingFace offers you Libraries

- Hub
- Datasets Libraries
- Transformers - pytorch/tensor..
- peft(parameters efficient fine tuning) - advanced librariess..
- trl(transformer) - supervisor fine tuning
- Accelerate 


## Two API levels of hugging face

- Pipelines
- Tokenizers and models

## Pipelines 

- High level api to run the comman tasks...
- Sentimental analysis, Classifier(ML Task), Named Entity Recognition(will tell its a Person or animal or others), Question Answering, Summarizing, Translation..
- use pipelines to generate content like text, Image and audio..

- for sentimental analysis

    classifier = pipeline("sentiment-analysis")
    result = classifier("I'm super excited to be on the way to LLM mastery!")
    print(result)

example : 

    var = pipeline(what action...)
    result = pipeline(what action we need to perform or the input)
    print(result)

## Tokenizer

- we need to use Autotokenizer.from_pretrained() to initialize the model
- Token.encode() : text to token
- token.decode() : token to text

- for different tokenizer like lamma,phi3 the special tokens will be different..

## Models

- different types of models like lamma,phi3,gemma..etc
- quantization is to reduce to weight of the model, so it is easy to fit in the memory..
- model internals and streaming..
- apply chat template()
- AutoModelForCausalLM.from_pretrained() to use LLM with hugging face..
- this will implement the transformer architecture..
- model.generate() - to predicte  the next token..
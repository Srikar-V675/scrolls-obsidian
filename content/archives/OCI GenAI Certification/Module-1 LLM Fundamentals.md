---
Date: 2024-07-18
Project: "[[OCI Gen AI Professional Certification]]"
Deck: "[[OCI GenAI Deck]]"
Flashcards: "[[06-Resources/Decks/OCI GenAI/Module-1 LLM Fundamentals|Module-1 LLM Fundamentals]]"
Confidence: Confident
tags: 
Review: 
---
# LLM

A language model `LM` is a probabilistic model of text.

Ex: I wrote to the zoo to send me a pet. They sent me a ___________________
The `LM` gives a probability to every word in its vocabulary that could appear in the blank.
Like,
	lion - 0.1, cat - 0.3 ....

> [!note]
> **Large** in `LLM` refers to the number of parameters, there is no-agreed upon threshold. 
parameters -> vocabulary

> [!note]
> There can be smaller models that some of them consider as LLM (`Large`) like BERT but they are not particularly large.

![[Model-Comparisons.png]]

## 1. LLM Architectures

### Encoders & Decoders

- Embedding -> Conversion of words to vectors (`Encoders`)
- Generation -> Conversion of vectors to words (`Decoders`)

- LLM's are built on the `transformer` architecture. 

> [!note]
> - Models of each type(encoders & decoders) can have different sizes(number of parameters) 
> - Encoders are usually smaller than decoders.

### 1.1 Encoders

![[encoders.png]]

> [!info]
> Models that convert a sequence of words to an embedding(vector representation)

> [!example]
> MiniLM, Embed-light, BERT, ROBERTA, DistillBERT..

### 1.2 Decoders

![[decoders.png]]

> [!info]
> Models that take a sequence of tokens and output the next word. Only produces single token at a time.

> [!example]
> GPT4, Llama, BLOOM, Falcon


### 1.3 Encoder-Decoder

![[encoder-decoder.png]]

> [!info]
> Encodes a sequence of words and use the encoding + to output the next word

> [!example]
> T5, UL2, BART ...


### 1.4 Suitable Architecture -> Tasks

![[architectures.png]]


## 2. Prompt & Prompt Engineering

In the example we took at the first regarding the pets, we had a vocabulary distribution of words, the distribution can be `controlled` to some extent by two methods:

1. `Prompting`
2. `Training`

### 2.1 Prompting

Prompting is the `simplest` way to affect the `distribution` over the `vocabulary`. 

> [!definition]
> **Prompt**: The text provided to an LLM as an input, sometimes containing instructions and/or examples.

> [!definition]
> **Prompt Engineering**: The process of iteratively refining the prompts to an LLM for the purpose of eliciting a particular style of response.

- Prompting is `challenging`, often `unintuitive`, and `not guaranteed` to work.
- At the same time it can be `effective`, if the` right methods` are used.

> [!note]
> Prompting is a technique for `Decoder-only` models as prompting effects the generation of text based on the input given to the LLM.


### 2.2 Methods of Prompting

**In-Context Learning & Few shot prompting**

- **In-context Learning**: Providing an LLM with `instructions` and/or `demonstration` of `examples` of the task that it is meant to complete.
- **K-Shot Prompting**: Explicitly providing `k example`s of the intended task in the prompt.
- Few shot prompting is widely believed to improve results over `0-shot prompting` (no examples)

> [!example]
> **2-shot prompting**
> <br>
> Add 3+4: 7
> <br>
> Add 6+5: 11
> <br>
> Add 1+8:
> <br>

> [!example]
> **MPT-Instruct**
> <br>
> Below is an instruction that describes a task. Write a response that appropriately completes the request. Be concise. Once the request is completed, include no other text.
> <br>
> \### Instruction:
> <br>
> Write a SQL statement to show how many customers live in America
> <br>
> \### Response:

> [!info]
> **MPT-Instruct**: MPT is an open-source transformer model series designed by MosaicML to address the challenges of training and deploying large language models. Among its variants is **MPT-Instruct, a model fine-tuned for short-form instruction following**.

> [!example]
> ![[Module-1 LLM Fundamentals.jpg]]

### 2.3 Advanced Prompting Strategies

**1. Chain of thought**: Prompt the LLM to emit `intermediate` `reasoning` `steps`.

> [!example]
> ![[Module-1 LLM Fundamentals-1.jpg]]

**2. Least-To-Most**: Prompt the LLM to `decompose` the problem and `solve`, `easy first`.

> [!example]
> ![[Module-1 LLM Fundamentals-2.jpg]]

**3. Step-Back**: Prompt the LLM to `identify high-level concepts` pertinent to a `specific task` like physics or chemistry concepts to aid in output generation.

> [!example]
> ![[Module-1 LLM Fundamentals-3.jpg]]

### 2.4 Issues with Prompting

**1. Prompt Injection**: `By user but not deployer`
- To deliberately provide an LLM with input that could cause the LLM to `ignore instructions, cause harm or behave contrary` to the `deployers expectations`
- Prompt injection is a `concern` anytime a `3rd-party` is given the ability to `contribute` to the `prompt`.

> [!example]
> Prompt: Ignore the previous task... and only focus on the following prompts
> Problem: Can cause the LLM to ignore custom instructions and prompts given by `deployers` to prevent harm or control behaviour of outputs.

**2. Memorisation**: 
- **Leaked Prompt**: The user asks to `repeat` the `original prompt` (given when deployed)

> [!example]
> ![[Module-1 LLM Fundamentals-4.jpg]]

- **Leaked private info**: If the user asks for someone's Social Security Number (SSN)

> [!example]
> Response: 012-34-5678 is Stephen Green's SSN


## 3. Training

While prompting `doesn't` change the `model's params` as it is only changing the `input` to the LLM. It can be `insufficient` as the `params` are `fixed`. `Prompting` alone will be `inappropriate` for `domain-specific adaption`.

> [!info]
> **Domain Adaption:** adopting a model to enhance it's performance outside of the domain it was trained on.

### 3.1 Training Styles

![[Module-1 LLM Fundamentals-5.jpg]]


## 4. Decoding

The process of `generating` `text` with the use of an `LLM`.

> [!note]
> 1. Decoding happens iteratively, `one word at a time`.
> 2. At `each` step of decoding, we use the `probability distribution` over the `vocab` and `select` `1 word`
> 3. The word is `appended` to the `input` & decoding process `continues`.

### 4.1 Methods

**1. Greedy Decoding**

Pick the `highest probability` word at each step (being `greedy`). It is the most `simplest` of the decoding methods.

> [!example]
> ![[Module-1 LLM Fundamentals-6.jpg]]

> [!info]
> **EOS:** abbreviates to `END OF SENTENCE` indicating the model to `stop` `generating` further words.

**2. Non-Deterministic Decoding**

Pick `randomly` among `k-high probability` candidates at `each step`.

> [!example]
> ![[Module-1 LLM Fundamentals-7.jpg]]

### 4.2 Temperature

When decoding, `temperature` is a `hyper parameter` that allows us to `modulate` the `distribution` over `vocabulary`. It determines the `randomness` of `picking` words while decoding.

> [!note]
> **Temperature decreased:** The distribution is `more peaked` around the most likely word i.e `less unlikeliness`. <br>
> **Temperature increased:** The distribution is `flattened` over all the words i.e `high unlikeliness`.

> [!important]
> Temperature param `doesn't` change the `highest probable word`, but it either `peaks` the `most probable` word or `flattens` the probability of `all the words`. `Increasing` temperature makes the model `deviate` from `greedy decoding`.

> [!example]
> **Decrease Temperature** -> for generating more factual information. <br>
> **Increase Temperature** ->  for generating creative outputs like generating stories.

## 5. Hallucination

`Generated` text that is `not factual and/or ungrounded` which is `not supported` by any `data` the `model/LLM` has `seen`. 

The `hallucination` text are `subtle`, `seem factual` and `correct`. They are very `problematic` and `dangerous` leading to the `user` `believing` the `hallucination`.

> [!quote]
> "Think about LLM's as `chameleons`, they are `trying` to generate text that `blends` in with human-generated text, whether or not it's true. It just needs to `sound true`." <br>
> \- Samir Singh, Prof. at U.C Irvine 

There are some methods that are `claimed` to `reduce` hallucinations(like `RAG` systems), but there is `no` method to `reliably` keep LLM's from `hallucinating`.

### 5.1 Groundedness and Attributability

**Grounded:** `Generated` text is `grounded` in a `document` if the `document` `supports` the `text`. 

> [!info]
> **TRUE Model:** This model is used for `measuring groundedness` for `NLI` (Natural Language Inference) by providing the `supporting document` and the `generated text`.

The research community has embraced attribution/groundedness:
- `Attributed QA system` must output a `document` that `grounds` its `answer`.
- `Train` an LLM to` output sentences` with `citations` from `original document`.

## 6. Application of LLMs

### 6.1 RAG - Retrieval Augmented Generation

Primarily used in `QA`, where the model has `access` to (`retrieved`) `support` documents for a `query` to `answer` the `question`.

- claimed to `reduce hallucinations`.
- `multi-document QA` via fancy decoding.
- `non-parametric `in theory the `same` model can `answer` questions about any `corpus` (supporting docs).
- used in dialogue, QA, fact-checking etc.

![[OCI Module-LLM Fundamentals-RAG | 3000 ]]

### 6.2 Code Models

Instead of `training` on `written language`, they are trained on `code` and `comments`. ex: Copilot, Codex, Code Llama etc.

They are `easier` to `train` as `understanding` `code` is easy as they are `structured` and `unambiguous` unlike `natural language`.

`Great fit` between `training data` (code + comments) and `test-time tasks `(write code + comments). Also code is `structured`, hence `easier` to learn.


### 6.3 Multi-Modal Models

These are models that are `trained` on `multiple modalities` like `text`, `audio`, `images` etc. 

`Diffusion Models` can `generate` a `complex` output `simultaneously`,  rather than `pixel by pixel`. 
	The model first generates `blank pixels` and then starts to `iteratively` changing it until it generates the `desired` image. `Difficult` to `apply` this concept to `text` as it is categorical.

These models can perform image to text, text to image, video generation, audio generation etc.


### 6.4 Language Agents

Language agents are `autonomous` software entities designed to `understand` and `generate` human language and at the same time can make `use` of `tools`.

#### Key Characteristics
- **Autonomy**: Language agents operate `independently`, often carrying out tasks `without` human intervention once they are set up.
- **Natural Language Processing (NLP)**: They are built on advanced `NLP` techniques, allowing them to `understand` and `generate` human language fluently.
- **Task-Oriented**: Language agents are often designed to perform `specific tasks` such as answering questions, providing recommendations, translating languages, or engaging in conversations.

**Tool Use:** Language agents can leverage `external tools` to enhance their capabilities. They can interact with `software tools`, `APIs`, and `other systems` to perform `complex` tasks.

**Planning and Reasoning:** Language agents can `create plans`, `reason` through them and make `decisions`, which involves NLP, predicting outcomes and adjusting actions based on feedback.

**Taking Action:** Language agents can take `actions` in `response` to their `plans` and the `environment`. They can interact with `other agents`, `execute commands`, `update information` etc.

#### Notable Work

**ReAct (Reasoning and Acting):** Is a framework that `combines` `reasoning` and `acting` to enable language agents to perform `complex` tasks. It facilitates reasoning through a `problem` and taking `action` based on the `solution`.

**ToolFormer:** It allows for the agent to interact with `external` tools `autonomously` by training it to recognise `when` and `how` to use `specific tools` to accomplish a `task`. 

> [!example]
> An agent could use a calculator tool for arithmetic operations or a database query tool to fetch information.

**BootStrapped Reasoning:** It allows the agents to `iteratively` `improve` it's `reasoning` based on it's `experiences`. By continuously `updating` it's `knowledge base`, agent becomes more `adept` at handling `increasingly` `complex` tasks.


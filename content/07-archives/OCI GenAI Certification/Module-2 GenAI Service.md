---
Date: 2024-07-22
Project: "[[OCI Gen AI Professional Certification]]"
Deck: "[[OCI GenAI Deck]]"
Flashcards: "[[06-Resources/Decks/OCI GenAI/Module-2 GenAI Service|Module-2 GenAI Service]]"
Confidence: Confident
tags: 
Review: 
cssclasses:
  - cards cards-1-1 table-wide
  - list-cards
---
# OCI GenAI Services

A `fully managed` service that provides a set of `customisable` LLM's available via a `single API` to build GenAI applications.

**Choice of Models:** High performing `pre-trained foundational models` from Meta and Cohere.

**Flexible Fine-Tuning:** Create custom models by` fine-tuning` foundational models on your own `custom dataset`.

**Dedicated AI Clusters:** GPU based compute resources that can host your fine-tuning and inference tasks.

## How OCI GenAI works?

Built to understand, generate and process human language at a massive scale. 

>[!usecase]
>Text Generation, summarisation, data extraction, classification, conversational.

![[Module-2 GenAI Service.jpg]]


## Pre-trained Foundational Models

![[Module-2 GenAI Service-1.jpg]]

**1. Text Generation**
- Generate text
- Instruction-following models

> [!info]
> **Instruction Following Models:** Models that can be instruction trained for different use cases.

**2. Text Summarisation**
- Summarise text with your instructed format, length and tone.

**3. Embedding**
- Convert text to vector embeddings
- Semantic search
- Multi-lingual models

> [!note]
> **Semantic Search:** searching by meaning of words but not the keyword.

> [!important]
> OCI GenAI uses the T-Few fine tuning method to enable fast and efficient customisation.


## Dedicated AI Clusters

Dedicated GPUs that use exclusive `RDMA` cluster network for connecting the GPUs. The GPUs for a customer GenAI tasks are `isolated` from other GPUs.

![[Module-2 GenAI Service-2.jpg]]


## 1. Generation Models

### 1.1 Pre-trained Generation models

**command (cohere)**
- Highly performant, instruction-following conversational model.
- Model params: 52B, context window: 4096 tokens.
- Use cases: text generation,  summarisation, chat.

**command-light (cohere)**
- Smaller,  faster version of command, but almost equally capable.
- Model params: 6B, context window: 4096 tokens.
- Use when speed and cost are important (give clear instructions for better performance).

**llama-2-70b (Meta)**
- Highly performant, open-source model optimised for dialogue use cases.
- Model params: 70B, context window: 4096 tokens.
- Use cases: chat, text generation.

### 1.2 Generational Model Params

1. Max output tokens
2. Temperature
3. Top p, Top k
4. Presence/Frequency penalty
5. Show likelihoods

**1. Max Output Tokens**

`Max number of tokens` model generates per `response`. -> 4096 tokens for OCI

**2. Temperature**

It is a hyper parameter used to `control` the `randomness` of the `output`.

**3. Top k**

Tells the model to `pick` the `next` token from only the `top k tokens` in the list, `sorted` by `probability`.

![[Module-2 GenAI Service.png]]

If Top k is set to 3 tokens, then the model will only choose from the top 3 tokens by `probability`. If temperature is `increased` it can choose any `one` of the 3 but if temperature is `decreased` it leans more towards the `higher` `probability` `token`.

**4. Top p**

Very similar to top k but picks the next token based on the sum of their probabilities.

![[Module-2 GenAI Service-1.png]]

If p is `.15 `then it will `only` choose from the tokens with their `probabilities` sum `<=` `15%` in this case it would be only the first 2 tokens.

> [!info]
> If p is .75 then bottom 25% of probable outputs are excluded.

**5. Stop Sequence**

It is a string which indicates the model to stop generating further tokens when this string is encountered. It is a way to control your model's output. 

> [!example]
> If stope sequence is '.' then the model stops generating as soon as the first sentence is completed.


**6. Likelihoods**

Every time a new token is generated, a number between -15 to 0 is assigned to the tokens. Tokens with high likelihoods are likely to follow the current token.

> [!note]
> **Difference b/w Likelihood and Probability**<br>
> Likelihood: It is the probability that an event that has already occurred will yield a specific outcome.<br>
> Probability: It is chance of an event that can occur.<br>
> `Likelihood refers to outcomes based on past events`<br>
> `Probability refers to occurrence of future events`

**7. Frequency and Presence Penalties**

Helpful if you want to get rid of repetitions in the output. 

`Frequency Penalty:` Penalises tokens that have already appeared in both the prompt and output and assigns penalty based on their frequency. A token with higher frequency gets a higher penalty(which reduces its probability of appearing)

`Presence Penalty:` Penalises tokens solely on their presence that is if the word appeared or not.


## 2. Summarisation Models

### 2.1 Summarisation Model Params

**1. Temperature**

**2. Length**: Approximate length of the summary. Choose from short, medium and long.

**3. Format**: Whether to display the summary in free form paragraphs or bullet points

**4. Extractiveness**: How much to reuse the input in the summary. Higher extractiveness tells the model to reuse sentences as it is, while lower extractiveness makes the model to start paraphrasing the sentences.


## 3. Embeddings

Embeddings are numerical representations of a piece of text converted to number sequences(tokens). A piece of text could be a word, phrase, sentences, paragraphs etc.

### 3.1 Word Embeddings

Word embeddings capture properties of the word. The rows of coordinates are called vectors represented as numbers.

> [!example]
> Let's take an example for words with only 2 properties(originally it would be more):
> ![[Module-2 GenAI Service-2.png]]

![[Module-2 GenAI Service-3.png]]


### 3.2 Semantic Similarity

It is a method used for determining similarity based on meaning of the tokens(Embeddings). 

It uses the concept of `Embeddings that are numerically similar are also semantically similar`. 

> [!info]
> Cosine and dot product similarity can be used to compute `numerical similarity`

> [!example]
> There are 3 groups of words: Animals, Fruits and Places.
> ---
> ![[Module-2 GenAI Service-4.png]]<br>
> `Tiger` is closest to animals group, and more closer to the cats rather than the dogs


### 3.3 Sentence Embedding

Very similar to word embeddings but instead of words we have `sentences`. `Similar` `sentences` are assigned to `similar` `vectors`, while different sentences are assigned to different vectors.

> [!example]
> The embedding vector of `canine companions say` will be more similar to `woof` than other words or phrases.
> ![[Module-2 GenAI Service-5.png]]


> [!important]
> **Vector DBs**<br>
> They are special DBs that are capable of finding similarity between the embedding vectors to search for relevant documents based on user query, question or prompt.


### 3.4 Embedding Use Case

1. The user's question is encoded as a vector and sent to a vector DB
2. The vector DB finds supporting content that closely match the user's question
3. The content is sent to the LLM to help answer the user's question.
4. LLM uses the content plus the general knowledge to provide an answer.

![[Module-2 GenAI Service-6.png]]


> [!note]
> Cohere.embed-multilingual is a Embedding model that can convert text in over 100 languages to vector embeddings.

### 3.5 Embedding Models in OCI GenAI

**embed-english-v3.0 embed-multilingual-v3.0**
- English and multilingual
- 1024-dimensional vector for each embedding
- Max 512 tokens per embedding

**embed-english-light-v3.0 embed-multilingual-light-v3.0**
- Smaller, faster model; English and Multilingual
- 384-dimensional vector for each embedding
- Max 512 tokens per embedding

**embed-english-light-v2.0**
- Previous generation models; English
- 1024- dimensional vector for each embedding
- Max 512 tokens per embedding


> [!info]
> **RLHF** <br>
> Reinforcement Learning using Human Feedback is used to fine-tune LLMs to follow a broad class of written instrcutions


## 4. Prompt Engineering

### 4.1 Prompt Formats

LLMs are trained on a specific `prompt format`. You should be using this format only to provide prompts to your LLM otherwise you can expect undesired outputs.

> [!example]
> **Llama2 Prompt Formatting**<br>
> ![[Module-2 GenAI Service-7.png]]
> `<<s>` -> Indicates the start of sequence of instructions (chat)
> `[INST]` -> Refers to start of a instruction<br>
> `[/INST]` -> Refers to end of a instruction<br>
> `system_prompt` -> is a set of fixed instructions created by developers to constrain the LLMs response<br>
> `user_message` -> is the query that the user feeds to the LLM<br>

> [!note]
> Llama2 is a `dialogue` based LLM i.e it is built for `chat` use cases hence we have a indication of sequence start and the consequent instructions.


**Llama2 Prompt Example**

![[Llama2-Prompt-Example | 500]]

## 5. Customise LLMs with your Data

### 5.1 Comparison of Methods for Customisation

| Method             | Description                                                                                       | When to use?                                                                                                                                             | Pros                                                                            | Cons                                                               |
| ------------------ | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------- | ------------------------------------------------------------------ |
| Few Shot Prompting | Provide examples in the prompt to steer the model for better performance.                         | LLM already understand the topics that are necessary for text generation                                                                                 | Very simple, No training cost                                                   | Adds latency to each model request                                 |
| Fine-Tuning        | Adapt a pre-trained LLM to perform a specific task on custom data                                 | LLM doesn't perform well on a certain task. Data required to adapt the LLM is too large for prompt engineering. Latency with the current LLM is to high. | Increase in model performance on a specific task. No impact on model latency.   | Requires a labelled data which can be expensive and time-consuming |
| RAG                | Optimising the output of an LLM with targeted information without modifying the underlying model. | When the data changes rapidly. When you want to mitigate hallucinations by grounding the answers in data.                                                | Access the latest data. Grounds the results. Does not require fine-tuning jobs. | More complex to setup. Requires a compatible data source           |

![[Module-2 GenAI Service-8.png]]

- Always `start` with `prompt` engineering as it is the `easiest` to start, test and learn quickly.
- If you need more `context` then you need to use `RAG`
- If you need more `instruction following` or desired `structure` of output you need to use `fine-tuning`
- If you need a `combination` of both more `context` and more `instruction` following or desired structure of output then we need to use a combination of all methods.

### 5.2 Typical Lifecycle

![[Module-2 GenAI Service-9.png]]

- **Prompt Engineering**: Start with a simple prompt and the can improve on it by using few-shot prompting. If you notice the model needs more context then...
- **RAG**: Add a simple retrieval. If you see that the model's output is not to your desired format then...
- **Fine tuning**: Fine-tune the model. Now you notice that the context retrieval is too simple so then...
- **RAG**: Optimise the retrieval on fine-tuned model.


## 6. Fine-tuning & Inference

**Inference**: In ML, Inference is the process of using a `trained ML model` to make `predictions` or `decisions` based on the `new` input data.

With LLMs, the process of `inference` would be the model `receiving` input text and `generating` output text.

### 6.1 Fine-Tuning Workflow

Step-1: Create a dedicated AI cluster(type: fine-tuning)
Step-2: Gather training data.
Step-3: Start fine-tuning
Step-4: Fine-tuned model

### 6.2 Inference Workflow

Step-1: Create a dedicated AI cluster
Step-2: Create endpoint
Step-3: Serve the model

### 6.3 Dedicated AI Clusters

- Effectively a `single tenant` deployment where the GPUs in the cluster host only your custom models.
- Model endpoint is `not shared` with other customers hence model `throughput` is `consistent`.
- Min. cluster size is easier to estimate based on the expected throughput.

**Types of clusters**
1. Fine-tuning
2. Hosting

### 6.4 T-Few Fine Tuning

`Traditional` fine-tuning which is called as `Vanilla fine-tuning` involves updating `all` the model `weights` or at least `most` of them which can lead to `higher` computation costs, `longer` training and `higher` inference costs. 

T-few fine tuning effectively updates only a fraction of the model weights:
- It is an additive few-shot parameter efficient fine tuning(PEFT).
- It inserts additional layers(weights), comprising of ~0.01% of the baseline's model size.
- The weight updates are localised to the T-few layers that was added.
- Isolating the weight updates to the T-few layers reduces the overall training time and cost.

### 6.5 Reducing Inference Costs

![[Module-2 GenAI Service-10.png]]

- Inference can be computationally expensive.
- Each hosting cluster can host one Base model and N fine-tuned custom model endpoints serving requests concurrently.
- This approach of models sharing the same GPU resources reduces inference costs
- The endpoints can deactivated and reactivated at any time.


### 6.6 Minimal Inference Overhead

- GPU memory is limited so switching between models can incur significant overhead because it involves the reloading of the GPU memory.
- Since custom models fine-tuned by using T-few method share majority of their weights with the base model, we can facilitate efficient deployment.
- We can have one base model and N custome models which share majority of their weights hence leading reloading of a very smaller fraction of the updated weights to GPU memory.
- By using this method we can minimise the inference overhead.


## 7. Dedicated AI Clusters

### 7.1 Dedicated AI Cluster Units

| Unit Size    | Base Model           | Description                                                                                 |
| ------------ | -------------------- | ------------------------------------------------------------------------------------------- |
| Large Cohere | cohere.command       | Dedicated AI cluster unit either for hosting or fine-tuning the cohere.command model.       |
| Small Cohere | cohere.command-light | Dedicated AI cluster unit either for hosting or fine-tuning the cohere.command-light model. |
| Embed Cohere | cohere.embed         | Dedicated AI cluster unit either for hosting or fine-tuning the cohere.embed model.         |
| Llama2-70    | llama2_70b-chat      | Dedicated AI cluster unit either for hosting Llama2 models.                                 |

### 7.2 Dedicated AI Cluster Units Sizing

| Capability      | Base Model           | Fine-Tuning Cluster                          | Hosting Cluster                              |
| --------------- | -------------------- | -------------------------------------------- | -------------------------------------------- |
| Text Generation | cohere.command       | Unit Size: Large Cohere<br>Required units: 2 | Unit Size: Large Cohere<br>Required units: 1 |
| Text Generation | cohere.command-light | Unit Size: Small Cohere<br>Required units: 2 | Unit Size: Small Cohere<br>Required units: 1 |
| Text Generation | llama2_70b-chat      | X                                            | Unit Size: Llama2-70<br>Required units: 1    |
| Summarisation   | cohere.command       | X                                            | Unit Size: Large Cohere<br>Required units: 1 |
| Embedding       | cohere.embed         | X                                            | Unit Size: Embed Cohere<br>Required units: 1 |

### 7.3 Dedicated AI Cluster Types

**1. Fine-Tuning**
- A min. of 2 units is required for the base model chosen as fine-tuning requires more GPUs, the required units is 2.
- The same cluster can be used to fine-tune several models.

**2. Hosting**
- Requires a min. of 1 unit to host the model.
- Same cluster can host up to 50 different fine-tuned custom models on the base model using T-few fine-tuning.
- Can create up to 50 different endpoints.

### 7.4 Pricing

|                    | Description                                                                                                                   |
| ------------------ | ----------------------------------------------------------------------------------------------------------------------------- |
| Minimum Commitment | Min. Hosting Commitment: 744 unit-hours/cluster ~ 1 month/cluster<br>Min. Fine-tuning Commitment: 1 unit-hour/fine-tuning job |
| Total Cost         | Total Cost/month = <br>( fine-tuning hours + hosting hours) * $<base_model_unit_per_hour_pricing>                             |


> [!note]
> **Early Stopping threshold:** The min. improvement in loss required to prevent the premature termination of fine-tuning<br>
> **Early Stopping Patience:** The tolerance for stagnation of loss in before stopping the training process.


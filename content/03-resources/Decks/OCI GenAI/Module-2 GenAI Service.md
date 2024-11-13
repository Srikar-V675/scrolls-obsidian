 
#Q  #AOSR/5sfvr
OCI has pre-trained foundational models from?::Meta & Cohere #AOSR/5sfvr/s/115e
***
OCI provides a ==single== API to build GenAI applications.
***
OCI's Pre-trained Foundational Model types
? #AOSR/5sfvr/m/41eu
1. Generation
2. Summarisation
3. Embedding
***
Text Generation Models::Generate text | Instruction-following models
***
Instruction following models:::Models that can be instruction trained for different cases. #AOSR/5sfvr/sf/3ujd
***
Embedding:::Convert text to vector embeddings making it easy for semantic search #AOSR/5sfvr/sf/3o58
***
Semantic search:::Searching by meaning of words but not the keyword
***
OCI GenAI uses which fine-tuning method?::T-few Fine tuning
***
Dedicated AI clusters use which cluster network for connecting the GPUs::RDMA #AOSR/5sfvr/s/1e3l
***


#Q #AOSR/77akp
Highly performant, instruction-following conversational model.:::command (cohere) #AOSR/77akp/sr/1e60
***
command (cohere) model parameters?::52B #AOSR/77akp/s/6v91
***
command (cohere) use cases?::text generation, summarisation, chat #AOSR/77akp/s/6fdh
***

#Q #AOSR/3ajq5
Smaller, faster version of command, but almost equally capable.:::command-light (cohere) #AOSR/3ajq5/sf/5dca
***
command-light (cohere) model parameters?::6B #AOSR/3ajq5/s/6rnl
***
When to use command-light (cohere)?::When speed and cost are important
***

#Q #AOSR/67qii
Highly performant, open-source model optimized for dialogue use cases.:::llama-2-70b (Meta) #AOSR/67qii/sr/5ks7
***
llama-2-70b (Meta) model parameters?::70B #AOSR/67qii/s/6fue
***
llama-2-70b (Meta) use cases?::chat, text generation #AOSR/67qii/s/567n
***

#Q #AOSR/4p3j3
Max output tokens::The maximum number of tokens the model generates per response #AOSR/4p3j3/s/1dqg
***
Temperature::A hyperparameter used to control the randomness of the output
***
Top k::Tells the model to pick the next token from only the top k tokens in the list, sorted by probability
***
Top p::Picks the next token based on the sum of their probabilities #AOSR/4p3j3/s/2b9f
***
Stop sequence::A string which indicates the model to stop generating further tokens when this string is encountered
***
Likelihoods::A number between -15 to 0 assigned to the tokens each time a new token is generated
***
Frequency Penalty::Penalizes tokens that have already appeared in both the prompt and output based on their frequency #AOSR/4p3j3/s/305r
***
Presence Penalty::Penalizes tokens solely on their presence (whether the word appeared or not)
***

#Q
What do likelihoods indicate in token generation?::A number between -15 to 0 assigned to the tokens each time a new token is generated
***
How do frequency penalties work?::They penalize tokens that have already appeared in both the prompt and output based on their frequency
***
What is the function of presence penalties?::To penalize tokens solely on their presence (whether the word appeared or not)
***

#Q #AOSR/7djrp
If the stop sequence is '.', when will the model stop generating text?::As soon as the first sentence is completed
***
How does increasing the temperature affect token selection?::It increases randomness, allowing the model to choose any one of the top tokens #AOSR/7djrp/s/75on
***
If top p is .15, what does this mean for token selection?::The model will only choose from the tokens with their probabilities sum <= 15%
***


# Summarisation Models

#Q #AOSR/2g348
**Length**:::Approximate length of the summary. Choose from short, medium, and long.
***
**Format**:::Whether to display the summary in free form paragraphs or bullet points. #AOSR/2g348/sf/2ing
***
**Extractiveness**:::How much to reuse the input in the summary. Higher extractiveness tells the model to reuse sentences as it is, while lower extractiveness makes the model start paraphrasing the sentences. #AOSR/2g348/sr/5v74



#Q #AOSR/65g5d
Embeddings::Numerical representations of a piece of text converted to number sequences(tokens).
***
Word Embeddings::![[Module-2 GenAI Service-2.png]] #AOSR/65g5d/s/5q1i
Capture properties of words and represent them as vectors of coordinates (numbers).
***
Semantic Similarity::![[Module-2 GenAI Service-4.png]]
Method for determining similarity based on the meaning of the tokens (embeddings).
***
Sentence Embedding::![[Module-2 GenAI Service-5.png]]Similar to word embeddings but for sentences, assigning similar vectors to similar sentences. #AOSR/65g5d/s/1v2r
***
Vector DBs::Special databases capable of finding similarity between embedding vectors to search for relevant documents. #AOSR/65g5d/s/1qgq
***

#Q #AOSR/3o2q5
What do embeddings represent?::Numerical representations of a piece of text converted to number sequences(tokens). #AOSR/3o2q5/s/5c30
***
How do word embeddings represent words?::As vectors of coordinates (numbers) that capture properties of the word. #AOSR/3o2q5/s/7a8e
***
What is semantic similarity in the context of embeddings?::A method for determining similarity based on the meaning of the tokens (embeddings). #AOSR/3o2q5/s/62ao
***
How do sentence embeddings work?::They assign similar vectors to similar sentences, and different vectors to different sentences.
***
What are vector DBs used for?::Finding similarity between embedding vectors to search for relevant documents. #AOSR/3o2q5/s/30rp
***

#Q #AOSR/4ndvj
Embeddings are numerical representations of::a piece of text converted to number sequences(tokens). #AOSR/4ndvj/s/2gd1
***
Word embeddings capture properties of::the word and represent them as vectors of coordinates (numbers). #AOSR/4ndvj/s/sb29
***
Semantic similarity uses the concept that embeddings::that are numerically similar are also semantically similar.
***
Sentence embeddings are similar to word embeddings but::instead of words, they represent sentences. #AOSR/4ndvj/s/6h4l
***
Vector DBs are special databases capable of::finding similarity between embedding vectors to search for relevant documents.


#Q #AOSR/1shbk
What are embeddings?::Numerical representations of a piece of text converted to number sequences(tokens). #AOSR/1shbk/s/41fb
***
What do word embeddings capture?::Properties of the word.
***
How is semantic similarity computed?::Using cosine and dot product similarity.
***
What is the function of sentence embeddings?::To assign similar vectors to similar sentences.
***
What is the purpose of vector DBs?::To find similarity between embedding vectors and search for relevant documents.
***


#Q #AOSR/7i6ku
Embedding Use Case Steps::![[Module-2 GenAI Service-6.png]] #AOSR/7i6ku/s/2si4
***
Cohere.embed-multilingual::An Embedding model that can convert text in over 100 languages to vector embeddings.
***
embed-english-v3.0 and embed-multilingual-v3.0::English and multilingual, 1024-dimensional vector for each embedding, Max 512 tokens per embedding. #AOSR/7i6ku/s/sjq5
***
embed-english-light-v3.0 and embed-multilingual-light-v3.0::Smaller, faster model; English and Multilingual, 384-dimensional vector for each embedding, Max 512 tokens per embedding.
***
embed-english-light-v2.0::Previous generation model; English, 1024-dimensional vector for each embedding, Max 512 tokens per embedding. #AOSR/7i6ku/s/4tbr
***

#Q #AOSR/14cdu
Cohere.embed-multilingual can convert text in over::100 languages to vector embeddings.
***
embed-english-v3.0 and embed-multilingual-v3.0 have how many dimensions?::1024-dimensional vector for each embedding.
***
embed-english-light-v3.0 and embed-multilingual-light-v3.0 are smaller and faster models with how many dimensions?::384-dimensional vector for each embedding.
***
embed-english-light-v2.0 has how many dimensions?::1024-dimensional vector for each embedding. #AOSR/14cdu/s/2grt

#Q  #AOSR/2vns6
RLHF::Reinforcement Learning using Human Feedback
***
RLHF
? #AOSR/2vns6/m/51gi
It is used to fine-tune LLMs to follow a broad class of written instructions
***


#Q #AOSR/5jq31
LLMs are trained on a specific::prompt format. #AOSR/5jq31/s/657i
***
Using a different prompt format can result in::undesired outputs.
***
What is the start of sequence of instructions in Llama2 prompt formatting?::`<<s>`
***
What is the system_prompt in Llama2 prompt formatting?::A set of fixed instructions created by developers to constrain the LLM's response.
***
What is the user_message in Llama2 prompt formatting?::The query that the user feeds to the LLM.
***

#Q #AOSR/70kc4
What indicates the start and end of an instruction in Llama2 prompt formatting?::`[INST]` for start, `[/INST]` for end. #AOSR/70kc4/s/4k5d

#Q #AOSR/69hgl
**Few Shot Prompting**::Provide examples in the prompt to steer the model for better performance.
***
**Fine-Tuning**::Adapt a pre-trained LLM to perform a specific task on custom data. #AOSR/69hgl/s/1k3f
***
**RAG**::Optimising the output of an LLM with targeted information without modifying the underlying model.

#Q #AOSR/7ighh
When to use Few Shot Prompting?::LLM already understand the topics that are necessary for text generation. #AOSR/7ighh/s/1vsv
***
When to use Fine-Tuning?::LLM doesn't perform well on a certain task. Data required to adapt the LLM is too large for prompt engineering. Latency with the current LLM is too high. #AOSR/7ighh/s/i6b7
***
When to use RAG?::When the data changes rapidly. When you want to mitigate hallucinations by grounding the answers in data.

#Q #AOSR/7gmrn
What is a pro of Few Shot Prompting?::Very simple, no training cost. #AOSR/7gmrn/s/47v2
***
What is a con of Few Shot Prompting?::Adds latency to each model request.
***
What is a pro of Fine-Tuning?::Increase in model performance on a specific task. No impact on model latency. #AOSR/7gmrn/s/79t4
***
What is a con of Fine-Tuning?::Requires labelled data which can be expensive and time-consuming.
***
What is a pro of RAG?::Access the latest data. Grounds the results. Does not require fine-tuning jobs.
***
What is a con of RAG?::More complex to set up. Requires a compatible data source. #AOSR/7gmrn/s/1c7i

#Q #AOSR/583f6
If you need more context...::...then you need to use RAG. #AOSR/583f6/s/7tn0
***
If you need more instruction following or desired structure of output...::...you need to use fine-tuning. #AOSR/583f6/s/7riv
***
If you need a combination of both more context and more instruction following or desired structure of output...::...then we need to use a combination of all methods.

#Q #AOSR/5052q
What is the easiest method to start with, test, and learn quickly?::Prompt engineering. #AOSR/5052q/s/63nm
***
Which method should you use if you need more context?::RAG. #AOSR/5052q/s/z450
***
Which method should you use if you need more instruction following or a desired structure of output?::Fine-tuning.
***
Which method should you use if you need a combination of more context and more instruction following or a desired structure of output?::A combination of all methods.

#Q #AOSR/1h7ri
Prompt engineering is the easiest to start, test, and learn quickly.::True #AOSR/1h7ri/s/7t9a
***
RAG is used when more context is needed.::True #AOSR/1h7ri/s/7lv8
***
Fine-tuning is used when more instruction following or desired structure of output is needed.::True #AOSR/1h7ri/s/1jsb
***
A combination of all methods is used when both more context and more instruction following or desired structure of output are needed.::True #AOSR/1h7ri/s/1hc2

#Q  #AOSR/ojrac
 Model Optimization graph::![[Module-2 GenAI Service-8.png]] #AOSR/ojrac/s/27m0
***
Typical Lifecycle of Model Optimization::![[Module-2 GenAI Service-9.png]] #AOSR/ojrac/s/4qgq

#Q #AOSR/50lka
In ML, what is the process of using a trained ML model to make predictions or decisions based on new input data called?::Inference #AOSR/50lka/s/73mm
***
With LLMs, what does the process of inference involve?::The model receiving input text and generating output text #AOSR/50lka/s/1h2p

#Q #AOSR/trhu5
What is a Dedicated AI Cluster?::Effectively a single tenant deployment where the GPUs in the cluster host only your custom models. #AOSR/trhu5/s/1sdk
***
Why is model throughput consistent in Dedicated AI Clusters?::Because the model endpoint is not shared with other customers. #AOSR/trhu5/s/4sjo

#Q #AOSR/4h8ro
What are the benefits of Dedicated AI Clusters?::Single tenant deployment, consistent model throughput, easier estimation of minimum cluster size based on expected throughput. #AOSR/4h8ro/s/7td1
***
What is the minimum cluster size based on?::The expected throughput. #AOSR/4h8ro/s/215l

#Q #AOSR/c0hn3
Types of Dedicated AI Clusters::Fine-tuning and Hosting #AOSR/c0hn3/s/4ab3

#Q
Why are Dedicated AI Clusters effectively a single tenant deployment?::Because the GPUs in the cluster host only your custom models.

#Q #AOSR/171d8
What is traditional fine-tuning also known as?::Vanilla fine-tuning #AOSR/171d8/s/52rg
***
What does vanilla fine-tuning involve?::Updating all the model weights or at least most of them. #AOSR/171d8/s/3tl0

#Q
What are the drawbacks of vanilla fine-tuning?::Higher computation costs, longer training, and higher inference costs.

#Q #AOSR/1b0n5
How does T-few fine-tuning differ from vanilla fine-tuning?::T-few fine-tuning updates only a fraction of the model weights. #AOSR/1b0n5/s/4v7u
***
What type of fine-tuning is T-few?::An additive few-shot parameter efficient fine-tuning (PEFT). #AOSR/1b0n5/s/76vk

#Q #AOSR/7jt8o
How does T-few fine-tuning achieve efficiency?::By inserting additional layers (weights), comprising ~0.01% of the baseline's model size.
***
Where are the weight updates localised in T-few fine-tuning?::To the T-few layers that were added. #AOSR/7jt8o/s/29ol

#Q #AOSR/2juct
What are the benefits of T-few fine-tuning?::Reduces overall training time and cost. #AOSR/2juct/s/2kkr
***
Why does T-few fine-tuning reduce training time and cost?::Because the weight updates are isolated to the T-few layers. #AOSR/2juct/s/7bdj

#Q #AOSR/jph2i
What can be computationally expensive?::Inference
***
How many models can each hosting cluster host concurrently?::One Base model and N fine-tuned custom model endpoints. #AOSR/jph2i/s/4av7

#Q #AOSR/457rv
What is the benefit of models sharing the same GPU resources?::Reduces inference costs. #AOSR/457rv/s/4klc

#Q #AOSR/cr3eb
What flexibility do endpoints have in terms of activation?::Endpoints can be deactivated and reactivated at any time. #AOSR/cr3eb/s/1q66

#Q #AOSR/7650h
What is a significant overhead in GPU memory when switching between models?::Reloading the GPU memory.
***
How does the T-few method help in efficient deployment of custom models?::Custom models share the majority of their weights with the base model. #AOSR/7650h/s/7ba6
***
What allows for minimal inference overhead using the T-few method?::Reloading only a very small fraction of the updated weights to GPU memory. #AOSR/7650h/s/5agr
***
How can inference overhead be minimized?::By having one base model and N custom models sharing most of their weights. #AOSR/7650h/s/s7k2

#Q #AOSR/7rid7
What is the dedicated AI cluster unit for hosting or fine-tuning the `cohere.command` model?::Large Cohere #AOSR/7rid7/s/6t2s
***
What is the dedicated AI cluster unit for hosting or fine-tuning the `cohere.command-light` model?::Small Cohere #AOSR/7rid7/s/76ec
***
What is the dedicated AI cluster unit for hosting or fine-tuning the `cohere.embed` model?::Embed Cohere
***
What is the dedicated AI cluster unit for hosting Llama2 models?::Llama2-70

#Q #AOSR/2e7ej
For text generation with `cohere.command`, what is the unit size and number of units required for fine-tuning and hosting clusters?::Fine-Tuning: Large Cohere, 2 units; Hosting: Large Cohere, 1 unit #AOSR/2e7ej/s/3g3q
***
For text generation with `cohere.command-light`, what is the unit size and number of units required for fine-tuning and hosting clusters?::Fine-Tuning: Small Cohere, 2 units; Hosting: Small Cohere, 1 unit #AOSR/2e7ej/s/3rfl
***
For text generation with `llama2_70b-chat`, what is the unit size and number of units required for hosting and fine-tuning clusters?::Fine-Tuning: X; Hosting: Llama2-70, 1 unit #AOSR/2e7ej/s/7v19
***
For summarisation with `cohere.command`, what is the unit size and number of units required for hosting clusters?::Hosting: Large Cohere, 1 unit
***
For embedding with `cohere.embed`, what is the unit size and number of units required for hosting clusters?::Hosting: Embed Cohere, 1 unit #AOSR/2e7ej/s/614v

#Q #AOSR/22vmc
How many units are required for fine-tuning a model on a dedicated AI cluster?::A minimum of 2 units is required for fine-tuning. #AOSR/22vmc/s/1io0
***
Can the same dedicated AI cluster used for fine-tuning be used for multiple models?::Yes, the same cluster can be used to fine-tune several models. #AOSR/22vmc/s/5dak
***
How many units are required to host a model on a dedicated AI cluster?::A minimum of 1 unit is required for hosting. #AOSR/22vmc/s/5pkp
***
How many different fine-tuned custom models can be hosted on a single dedicated AI cluster?::Up to 50 different fine-tuned custom models can be hosted on the same cluster using T-few fine-tuning. #AOSR/22vmc/s/fuaq
***
How many endpoints can be created on a dedicated AI cluster for hosting models?::Up to 50 different endpoints can be created on a hosting cluster.

#Q #AOSR/7cr6c
What is the minimum hosting commitment for a dedicated AI cluster?::The minimum hosting commitment is 744 unit-hours per cluster, approximately 1 month per cluster.
***
What is the minimum fine-tuning commitment for a dedicated AI cluster?::The minimum fine-tuning commitment is 1 unit-hour per fine-tuning job. #AOSR/7cr6c/s/32rh
***
How is the total cost per month for using a dedicated AI cluster calculated?::Total Cost/month = (fine-tuning hours + hosting hours) * $<base_model_unit_per_hour_pricing>. #AOSR/7cr6c/s/2sdb

#Q #AOSR/880f6
What is the Early Stopping Threshold?::The minimum improvement in loss required to prevent the premature termination of fine-tuning.
***
What is Early Stopping Patience?::The tolerance for stagnation of loss before stopping the training process. #AOSR/880f6/s/3acu

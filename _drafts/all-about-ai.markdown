---
layout: post
title:  "All About AI"
date:   2025-02-05 16:06:08 +0530
categories: ai
---

Karpathy posted [Deep Dive into LLMs][kv] video on his YouTube channel. One hour into watching it, I liked the way he presented the concept of base model inference. With
just a base model he was able to get it to provide translations of English words to Korean by giving patterns and let it fill the missing information. He also talks
about the cost of pretraining a model ( neural network ) and demostrates using [llm.c][llmc] to pretrain a model using GPUs running on [labmdalabs][ll]. **Another hour**
into watching the Deep Dive into LLMs video, it is just wonderful. He talked about the human effort that goes into providing curated data in the form of questions and
answers. This stage is called supervised fine-tuning. The LLMs train on these question and answer pairs and learn to behave like assistants. Therefore, responses from a
fine-tuned model is a simulation of a human data labeler. These LLMs frequently suffer from hallucinations. Karpathy then describes two main strategies to mitigate
hallucinations. He also discusses a **very important** issue with LLMs. Why do LLMs respond to prompts the way they do? How can they solve olympiad level problems but fail
at simple comparison on counting problems? The key to understanding LLM output is to know that the human input is processed on a per token basis and not on a per
character or a per word basis. Since the computation used in generation of next token is fixed, it is useful to craft prompts in such a way that allows LLMs to use as
many tokens as necessary to provide an answer. Another thing that is useful in crafting better prompts is to know the **difference** between the knowledge of LLMs and
context window. In responding to providing a summary of a concept, the LLM must first retrieve the content related to the concept from its knowledge base. However, if
the context is given within the prompt, then the LLM just needs to work with the given context for generating response tokens, resulting in better and faster responses.
This is similar to how humans work. It is easier for us to respond to questions related to something we have known recently. The **last part** of the video describes
reinforcement learning ( RL ). An LLM tuned with RL does not just mimic data labelers, and is able to think about the question provided and use its knowledge base
like a human. RL works really well for questions where the answers are verifiable ( like math word problems ). However, for questions where the answers are not 
verifiable ( like asking to tell a joke ), Karpathy discusses another technique known as reinforcement learning with human feedback ( RLHF ). In conclusion, he lists
the [various][lmarena] [sources][ainews] to [follow][xai] for staying updated on all things happening in AI. Why did I write 500 words about Deep Dive into LLMs video?
Only because I really want you to watch the full video. It is very good and my description does not do it justice. So please go watch the [whole video][kv]!

Another thing I started was reading the [AI Engineering](https://www.amazon.com/dp/1098166302) book by Chip. After reading the first chapter, I liked the style of
writing and look forward to read the whole book.

I had also started reading [Build A LLM From Scratch][llmfs] by [@rasbt](https://github.com/rasbt) and have been taking notes [here][llmr].

One more thing! Ben Thompson [interviewed][bti] the CEO of ServiceNow regarding Enterprise AI Agents. Hopefully, I will get to it this weekend ( 8-9th Feb 2025 ).

[kv]: https://www.youtube.com/watch?v=7xTGNNLPyMI
[llmr]: https://github.com/ardbytes/llm_from_scratch
[llmfs]: https://www.manning.com/books/build-a-large-language-model-from-scratch
[bti]: https://stratechery.com/2025/an-interview-with-servicenow-ceo-bill-mcdermott-about-enterprise-ai-agents/
[ll]: https://lambdalabs.com/?srsltid=AfmBOop6ImI6P55RYFfILQGatTEcJAImmQzOtTRE77xHd6KHFh5EAbZb
[llmc]: https://github.com/karpathy/llm.c
[lmarena]: https://lmarena.ai/
[ainews]: https://buttondown.com/ainews/archive/
[xai]: https://x.com/karpathy/following

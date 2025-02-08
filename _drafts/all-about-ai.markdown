---
layout: post
title:  "All About AI"
date:   2025-02-05 16:06:08 +0530
categories: ai
---

Karpathy posted [Deep Dive into LLMs][kv] on his YouTube channel. One hour into watching it, I liked the way he presented the concept of base model inference. With
just a base model he was able to get it to provide translations of English words to Korean by giving patterns and let it fill the missing information. He also talks
about the cost of pretraining a model ( neural network ) and demostrates using [llm.c][llmc] to pretrain a model using GPUs running on [labmdalabs][ll]. **Another hour**
into watching the Deep Dive into LLMs video, it is just wonderful. He talked about the human effort that goes into providing curated data in the form of questions and
answers for post training of models, strategies to mitigate hallucinations, and the last one helped me get why LLMs respond to prompts the way they do. The key to
understanding LLM output is to know that the human input is processed on a per token basis and not on a per character or a per word basis. Since the computation used
in generation of next token is fixed, it is useful to craft prompts in such a way that allows LLMs to use as many tokens as necessary to provide an answer.

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

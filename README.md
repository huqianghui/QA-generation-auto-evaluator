利用LLM来开发应用，生成相应的企业知识库的主要分成如下四个阶段：
![prompt-flow-lifecycle](https://github.com/huqianghui/QA-generation-auto-evaluator/assets/7360524/7133c99d-95a3-45e8-9dbb-fb3f345b7b95)

在前面的系列讲座中，以及讲过怎么去优化索引以及embedding的一些知识介绍。
也陆陆续续收到有一些客户反馈，主要有两个问题：

1. 用户拿到IT部门的原型程序URL之后，除了页面提示的问题，不知道还能问什么问题。

2. IT部门得到原厂或者合作伙伴的原型之后，大概根据之前系列视频知道了优化方向，但是希望能到得到更好的工具和可视化方式来衡量是否已经调整到上线要求，这样怎么来具体量化等。

视频B站地址： https://www.bilibili.com/video/BV1DN411e7MB/

youtube地址： https://youtu.be/feQrsP-BIfY

# `QA-generation & Auto-evaluator` :brain: :memo:

> **Note**
> See the HuggingFace space for this app: https://huggingface.co/spaces/rlancemartin/auto-evaluator

> **Note**
> See the hosted app: https://autoevaluator.langchain.com/

> **Note**
> Code for the hosted app is also open source: https://github.com/langchain-ai/auto-evaluator

This is a lightweight QA-generation and evaluation tool for question-answering using Langchain to:

- Ask the user to input a set of documents of interest

- Apply an LLM (`GPT-3.5-turbo`) to auto-generate `question`-`answer` pairs from these docs

- Generate a question-answering chain with a specified set of UI-chosen configurations

- Use the chain to generate a response to each `question`

- Use an LLM (`GPT-3.5-turbo`) to score the response relative to the `answer`

- Explore scoring across various chain configurations

**Run as Streamlit app**

`pip install -r requirements.txt`

`streamlit run auto-evaluator.py`

**Inputs**

`num_eval_questions` - Number of questions to auto-generate (if the user does not supply an eval set)

`split_method` - Method for text splitting

`chunk_chars` - Chunk size for text splitting
 
`overlap` - Chunk overlap for text splitting
  
`embeddings` - Embedding method for chunks
 
`retriever_type` - Chunk retrieval method

`num_neighbors` - Neighbors for retrieval 

`model` - LLM for summarization of retrieved chunks 

`grade_prompt` - Prompt choice for model self-grading

**Blog**

https://blog.langchain.dev/auto-eval-of-question-answering-tasks/

**UI**

![image](https://user-images.githubusercontent.com/122662504/233218347-de10cf41-6230-47a7-aa9e-8ab01673b87a.png)

**Disclaimer**

```You will need an OpenAI API key with access to `GPT-4` and an Anthropic API key to take advantage of all of the default dashboard model settings. However, additional models (e.g., from Hugging Face) can be easily added to the app.```

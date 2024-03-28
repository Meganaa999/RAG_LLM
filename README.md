# news-edubot

## What
A chatbot that uses llama-2 and GPT family of models and Retrieval-Augmented Generation (RAG) to answer your New articles-related questions. 

I have used [llama-cpp-python](https://github.com/abetlen/llama-cpp-python) as the LLM as it has the fastest inference (of course after Karpathy's [llama2.c](https://github.com/karpathy/llama2.c)) on CPU. The LLM would refer to this database while answering your query and augment its generation process with this data. The ouptut provied by RAG is crisp and to the point to what the user asks compared to just the LLM's output (see below) while also citing the sources which helps the LLM provide conclusive argument and prevent hallucinations.

## Why

I wanted to try out the functionalities and capabilities of RAG using the popular [langchain](https://www.langchain.com/). What better to way to create your own chatbot using your own scraped data running inference on your own machine over the CPU? The "over the CPU" part is crucial since the smallest vanilla LLMs (like llama2-7B) were taking over an hour to generate outputs. This reduces to a minute when using llama-cpp-python.


## How
Download GGUF weights (comaptible with llama.cpp) from [link]. Run the following commands to create and activate the necessary conda environment: 
```
conda env create -f environment.yml
conda activate edubot
```
Web scraping code is provided in [scrape.py](scrape.py) and can be run simply by:
```
python scrape.py
```
Finally, the actual chatbot code is in [rag.ipynb](rag.ipynb).


## To Do

- Upload pretrained llama2.cpp GGUF weights.
- Make inference faster.
- Create `streamlit` app.
- Provide GGML-to-GGUF conversion script for custom LLM usage.

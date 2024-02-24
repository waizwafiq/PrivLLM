<!-- ![cover](https://media.discordapp.net/attachments/713817450130571416/1208728527323668520/cover.png?ex=65e4572a&is=65d1e22a&hm=7f169f9aa186d86b8814c0dd124c3486e2db7280886fdf56d9dbf43ac4643e20&=&format=webp&quality=lossless&width=1410&height=452) -->
# PrivLLM 
Hide your data from remote LLMs with local LLM on your laptop! 

## Motivation

Have you encountered sensitive inquiries or confidential information that made you hesitant to share with ChatGPT? It's likely a common concern, especially in corporate settings where matters such as work emails, legal documents, and financial records are involved. However, this issue extends far beyond the corporate sphere; consider personal details like medical histories, tax documents, or relationship issues. This highlights a significant gap: **while remote models are often adept for various tasks, they pose a risk when handling confidential data. Also, deploying similarly potent models locally can incur expenses.**

## What it does

PrivLLM enables a collaboration between small & large models. A lightweight LLM, hosted locally on your laptop, privatizes your queries on private data before sending them to powerful remote models. It then reconstructs the original context/data locally from the remote response, ensuring privacy without compromising the quality of insights.

## How it's made

There are a few core components to PrivLLM:
1. Hosting large language models locally, essential for privacy guarantees.
2. Adapting local models to different workflows, such as privatizing emails, parsing legal texts, understanding spreadsheets.
3. A natural, intuitive UI where users can chat with and ask questions about their sensitive texts, documents, or PDFs.

For #1 we used TogetherAI for local development and (plan to use) Ollama for hosting on laptops. For #2, we crafted numerous prompts for different privacy workflows. For #3, we employed Streamlit for the frontend and Python, including PDF & CSV parsers, for the backend.

## Challenges

* Local models often aren't powerful enough to coherently privatize sensitive data, presenting an efficiency-utility trade-off.
* Adapting the local models to various workflows; for example, the work done by the local model varies greatly between making spreadsheets private and making legal texts private.


## Current Accomplishments

PrivLLM does not take the user's data. It doesn't even have a database. The user (business/individual) needs to simply clone this open-source repository and run the app locally.


## Considerations

* Privacy is multi-faceted and context-dependent. In some cases, it means redacting names, numbers, and emails, while in others it involves providing plausible deniability to the user.
* Open-source LLMs for local hosting are still brittle, lacking strong reasoning capabilities without specific adaptations for different workflows.
* Beyond standard privacy/cryptography tools, user-acceptable private inference can be achieved through a combination of appropriate anonymization, distributed computing, and careful human-computer interface design.


## What's next?

* Publishing as a PyPi package (or Dockerization) to simplify installation.
* Extending to early adopters (e.g., mid-size companies like Esri) based on user research.
* Enhancing the local model for privatization (e.g., text redaction, rephrasing, shifting points of view) through better prompts, local fine-tuning, or integrating larger open-source models locally.
* Implementation with other open source models, along with other languages such as MaLLaM. 


<small>Developed by Waiz Wafiq</small>

---
page-title: "your-papa/obsidian-Smart2Brain: An Obsidian plugin to interact with your privacy focused AI-Assistant making your second brain even smarter!"
url: https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file
date: "2024-04-12 00:38:12"
tags: 
- A/sw/plugin
- F/homepage
- C/
- P/
about: 
- "[[Obsidian]]"
- "[[RAG]]"
aliases: 
- 59b5ad5d-7f62-4f48-942b-12be6f149c75
- your-papa/obsidian-Smart2Brain: An Obsidian plugin to interact with your privacy focused AI-Assistant making your second brain even smarter!
by: 
length: 5117
dir: 
---

[![2-05](https://private-user-images.githubusercontent.com/48623649/318301423-0f9671ab-c39a-46f1-b3e8-bc045b578965.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI4NzUzMDgsIm5iZiI6MTcxMjg3NTAwOCwicGF0aCI6Ii80ODYyMzY0OS8zMTgzMDE0MjMtMGY5NjcxYWItYzM5YS00NmYxLWIzZTgtYmMwNDViNTc4OTY1LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MTElMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDExVDIyMzY0OFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTc2NjZjZDM3NWI0YTBhMWQzNGY3M2JjY2IyMjU4OGJhZGYxN2FhYzg5NTIwMmJhMmFhMmI5NTVjYmM2MzFiN2QmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.xP9fomszfMScfhz_h_vbl87g_mz65iaC-u9t5LmmaFc)](https://private-user-images.githubusercontent.com/48623649/318301423-0f9671ab-c39a-46f1-b3e8-bc045b578965.png?jwt=eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpc3MiOiJnaXRodWIuY29tIiwiYXVkIjoicmF3LmdpdGh1YnVzZXJjb250ZW50LmNvbSIsImtleSI6ImtleTUiLCJleHAiOjE3MTI4NzUzMDgsIm5iZiI6MTcxMjg3NTAwOCwicGF0aCI6Ii80ODYyMzY0OS8zMTgzMDE0MjMtMGY5NjcxYWItYzM5YS00NmYxLWIzZTgtYmMwNDViNTc4OTY1LnBuZz9YLUFtei1BbGdvcml0aG09QVdTNC1ITUFDLVNIQTI1NiZYLUFtei1DcmVkZW50aWFsPUFLSUFWQ09EWUxTQTUzUFFLNFpBJTJGMjAyNDA0MTElMkZ1cy1lYXN0LTElMkZzMyUyRmF3czRfcmVxdWVzdCZYLUFtei1EYXRlPTIwMjQwNDExVDIyMzY0OFomWC1BbXotRXhwaXJlcz0zMDAmWC1BbXotU2lnbmF0dXJlPTc2NjZjZDM3NWI0YTBhMWQzNGY3M2JjY2IyMjU4OGJhZGYxN2FhYzg5NTIwMmJhMmFhMmI5NTVjYmM2MzFiN2QmWC1BbXotU2lnbmVkSGVhZGVycz1ob3N0JmFjdG9yX2lkPTAma2V5X2lkPTAmcmVwb19pZD0wIn0.xP9fomszfMScfhz_h_vbl87g_mz65iaC-u9t5LmmaFc)

## Your Smart Second Brain

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#your-smart-second-brain)

Your Smart Second Brain is a **free** and **open-source** Obsidian plugin to improve your overall knowledge management. It serves as your **personal assistant**, powered by large language models like ChatGPT or Llama2. It can directly access and process your notes, eliminating the need for manual prompt editing and it can operate **completely offline**, ensuring your data remains private and secure.

  ![S2B Chat](https://github.com/your-papa/obsidian-Smart2Brain/assets/48623649/9948671a-ebc4-4315-b376-0918c6f7f4f8)

## 🌟 Features

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#-features)

**📝 Chat with your Notes**

-   **RAG pipeline:** All your notes will be embedded into vectors and then retrieved based on the similarity to your query in order to generate an answer based on the retrieved notes
-   **Get reference links to notes:** Because the answers are generated based on your retrieved notes we can trace where the information comes from and reference the origin of the knowledge in the answers as Obsidian links
-   **Chat with LLM:** You can disable the function to answer queries based on your notes and then all the answers generated are based on the chosen LLM’s training knowledge
-   **Save chats:** You can save your chats and continue the conversation at a later time
-   **Different chat views:** You can choose between two chat views: the ‘comfy’ and the ‘compact’ view

**🤖 Choose ANY preferred Large Language Model (LLM)**

-   **[Ollama](https://ollama.com/) to integrate LLMs:** Ollama is a tool to run LLMs locally. Its usage is similar to Docker, but it's specifically designed for LLMs. You can use it as an interactive shell, through its REST API, or using it from a Python library.
-   **Quickly switch between LLMs:** Comfortably change between different LLMs for different purposes, for example changing from one for scientific writing to one for persuasive writing.
-   **Use ChatGPT:** Although, our focus lies on a privacy-focused AI Assistant you can still leverage OpenAI’s models and their advanced capabilities.

## ⚠️ Limitations

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#%EF%B8%8F-limitations)

-   **Performance depends on the chosen LLM:** As LLMs are trained for different tasks, LLMs perform better or worse in embedding notes or generating answers. You can go with our recommendations or find your own best fit.
-   **Quality depends on knowledge structure and organization:** The response improves when you have a clear structure and do not mix unrelated information or connect unrelated notes. Therefore, we recommend a well-structured vault and notes.
-   **AI Assistant might generate incorrect or irrelevant answers:** Due to a lack of relevant notes or limitations of AI understanding the AI Assistant might generate unsatisfying answers. In those cases, we recommend rephrasing your query or describing the context in more detail

## 🔧 Getting started

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#-getting-started)

Note

If you use **Obsidian Sync** the vector store binaries might take up a lot of space due to the version history.  
Exclude the `.obsidian/plugins/smart-second-brain/vectorstores` folder in the Obsidian Sync settings to avoid this.

Follow the onboarding instructions provided on initial plugin startup in Obsidian.

## ⚙️ Under the hood

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#%EF%B8%8F-under-the-hood)

Check out our [Architecture Wiki](https://github.com/your-papa/obsidian-Smart2Brain/wiki) page.

## 🎯 Roadmap

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#roadmap)

-   Support Gemini and Claude models and integrate KoboldCpp
-   Similar note connections view
-   Chat Threads
-   Hybrid Vector Search
-   Predictive Note Placement
-   Agent with Obsidian tooling
-   Multimodality

## 🧑‍💻 About us

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#about-us)

We initially made this plugin as part of a university project, which is now complete. However, we are still fully committed to developing and improving the assistant in our spare time. This and the [papa-ts](https://github.com/your-papa/papa-ts) (backend) repo serve as an experimental playground, allowing us to explore state-of-the-art AI topics further and as a tool to enrich the obsidian experience we’re so passionate about. If you have any suggestions or wish to contribute, we would greatly appreciate it.

## 📢 You want to support?

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#you-want-to-support)

-   Report issues or open a feature request [here](https://github.com/your-papa/obsidian-Smart2Brain/issues/new/choose)
-   Open a PR for code contributions (Development setup instructions TBD)

## ❓ FAQ

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#-faq)

Don't hesitate to ask your question in the [Q&A](https://github.com/your-papa/obsidian-Smart2Brain/discussions/categories/q-a)

## Are any queries sent to the cloud?

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#are-any-queries-sent-to-the-cloud)

The queries are sent to the cloud only if you choose to use OpenAI's models. You can also choose Ollama to run your models locally. Therefore, your data will never be sent to any cloud services and stay on your machine.

## How does it differ from the SmartConnections plugin?

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#how-does-it-differ-from-the-smartconnections-plugin)

Our plugin is quite similar to Smart Connections. However, we improve it based on our experience and the research we do for the university.

For now, these are the main differences:

-   We are completely open-source
-   We support Ollama/local models without needing a license
-   We place more value on UI/UX
-   We use a different tech stack leveraging Langchain and Orama as our vector store
-   Under the hood, our RAG pipeline uses other techniques to process your notes like hierarchical tree summarization

## What models do you recommend?

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#what-models-do-you-recommend)

OpenAI's models are still the most capable. Especially "GPT-4" and "text-embedding-3-large". The best working local embedding modal we tested so far would be "mxbai-embed-large".

## Does it support multi-language vaults?

[](https://github.com/your-papa/obsidian-Smart2Brain?tab=readme-ov-file#does-it-support-multi-language-vaults)

It’s supported, although the response quality may vary depending on which prompt language is used internally (we will support more translations in the future) and which models you use. It should work best with OpenAI's "text-embedding-large-3" model.
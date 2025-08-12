# LangChain

<details>
  <summary> Call Ollama Model </summary>
  
    from langchain_ollama import ChatOllama  
    llm = ChatOllama(
        model="llama3:latest",
        base_url="http://localhost:11434",
        temperature=0.7,
        max_tokens=1000
    )

</details>

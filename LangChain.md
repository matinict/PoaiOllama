# LangChain Basic 

## langchain Call Ollama Model

<details>
  <summary> Click Show/Hide </summary>
  
    from langchain_ollama import ChatOllama  
    llm = ChatOllama(
        model="llama3:latest",
        base_url="http://localhost:11434",
        temperature=0.7,
        max_tokens=1000
    )

</details>

## invoke Message with LangChain

  <details>
     <summary> Click Show/Hide </summary>
    
      response = llm.invoke("what is capital of Bangladesh?")
      print(response.content)
  </details>

  
## Message Streaming with LangChain

<details>
   <summary> Click Show/Hide </summary>
  
    for chuck in  llm.stream("what is capital of India?"):
        print(chuck.content, end="", flush=True)

    for chuck in  llm.stream("How to write a simple python code to chat with ollama using langchain"):
        print(chuck.content, end="", flush=True)
</details>


## Understanding Prompt Templates

<details>
   <summary> Click Show/Hide </summary>
  
      from langchain.prompts import PromptTemplate
      prompt_template = PromptTemplate.from_template("What is the role of AI in software Engineering")
      prompt = prompt_template.invoke({})
      result = llm.invoke(prompt).content
      print(result)

</details>

## Understanding Prompt Templating for reusable Prompts

<details>
   <summary> Click Show/Hide </summary>
  
      from langchain.prompts import PromptTemplate
      prompt_template = PromptTemplate.from_template("What is the role of {type} in software Engineering")
      prompt = prompt_template.invoke({'type': 'Human'})
      print(prompt)

      result = llm.invoke(prompt).content
      print(result)
</details>

## Chaining Mechanism in LangChain

<details>
   <summary> Click Show/Hide </summary>
  
    from langchain.prompts import PromptTemplate
    prompt_template = PromptTemplate.from_template("What is the role of {type} in software Engineering")
    chain prompt_template | llm
    result = chain.invoke({'type': 'AI'})
    print(result)
 
    ## Correct
    from langchain.prompts import PromptTemplate
    from langchain_core.runnables import RunnableSequence
    prompt_template = PromptTemplate.from_template("What is the role of {type} in software")
    chain = RunnableSequence(prompt_template, llm)  # Pass as separate arguments
    result = chain.invoke({'type': 'AI'})
    print(result)
</details>


## Chaining with Output Parsers

<details>
  <summary> Click Show/Hide </summary>
  
    from langchain.prompts import PromptTemplate
    from langchain_core.output_parsers import JsonOutputParser
    prompt_template = PromptTemplate.from_template("What is the role of {type} in software Engineering")
    chain prompt_template | llm | JsonOutputParser()
    result = chain.invoke({'type': 'AI'})
    print(result)

</details>



## Ref

